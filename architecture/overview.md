# Arquitetura do Sistema — Search CNPJs

## Visão geral

Sistema de **página única de busca**: o usuário insere um CNPJ em um campo e recebe, em um só lugar, os dados oficiais da empresa (API Open CNPJ) mais o enriquecimento de dados encontrados na web (DuckDuckGo).

**Não há** cadastro de usuário, autenticação, múltiplas telas ou banco de dados. O fluxo é simples: consultar um CNPJ e exibir o resultado.

## Camadas e responsabilidades

```
src/
├── routes/                    # Rotas SvelteKit (SSR) — orquestração HTTP
│   ├── +page.svelte           # Página única com o campo de busca e o resultado
│   ├── +page.server.ts        # Recebe o CNPJ e chama a orquestração
│   └── ...
├── lib/
│   ├── server/                # Código executado SOMENTE no servidor
│   │   ├── clients/           # Integrações externas isoladas
│   │   │   ├── open-cnpj.client.ts   # Cliente da API Open CNPJ
│   │   │   └── duckduckgo.client.ts  # Cliente de busca DuckDuckGo
│   │   ├── services/          # Regras de domínio e orquestração
│   │   │   ├── cnpj-search.service.ts      # Consulta + enriquecimento (fluxo principal)
│   │   │   └── enrichment.service.ts       # Lógica do enriquecimento DDG
│   │   └── cache/             # Cache em memória/arquivo (sem banco)
│   ├── types/                 # Tipos derivados do contrato da API Open CNPJ
│   │   └── cnpj.ts
│   └── components/            # Componentes de interface (ex: resultado do CNPJ)
└── app.css                    # Estilos globais
```

- **`routes/`** — não contém regras de negócio; apenas recebe o CNPJ, chama os serviços e entrega dados para a interface.
- **`lib/server/`** — concentra a lógica de domínio e as integrações externas, isoladas da interface e das rotas.
- **`lib/types/`** — shape dos dados do CNPJ com base no contrato da Open CNPJ (fonte da verdade de tipos).
- **`lib/components/`** — componentes de apresentação, sem lógica de integração.

## Fluxo de dados

```
Usuário
   │
   ▼
[+page.svelte]  insere o CNPJ (formatação de entrada)
   │
   ▼
[+page.server.ts]  valida e envia o CNPJ
   │
   ▼
[cnpj-search.service.ts]  ← orquestra o fluxo principal
   │
   ├── 1. Validação do CNPJ (dígitos verificadores e formato)
   │
   ├── 2. [open-cnpj.client.ts] → GET https://api.opencnpj.org/{cnpj}
   │         → retorna dados oficiais (razão social, email, telefone, endereço, etc.)
   │
   ├── 3. [enrichment.service.ts]  (se a consulta anterior foi OK)
   │         → busca no DuckDuckGo a razão social + dados da Open CNPJ
   │         → coleta links/trechos (redes sociais, contatos, site)
   │
   ├── 4. [cache]  grava o resultado para consultas futuras do mesmo CNPJ
   │
   ▼
[+page.svelte]  exibe: dados oficiais + seção de enriquecimento
```

## Tratamento de erros

| Cenário | Comportamento |
|---|---|
| CNPJ inválido (formato/dígitos) | Mensagem de validação, sem chamada externa |
| Open CNPJ retorna 404 | Exibe "CNPJ não encontrado" |
| Open CNPJ timeout/erro | Mensagem de erro amigável |
| DuckDuckGo bloqueia/timeout | **Degradação graciosa:** exibe dados oficiais; enriquecimento marcado como "indisponível" |

## Decisões de arquitetura

- **Sem banco de dados:** cache em memória/arquivo no servidor (ver ADR-003).
- **Sem autenticação/cadastro:** sistema de página única para busca pública.
- **SSR:** as chamadas externas acontecem no servidor, protegendo a lógica e o fluxo.
- **Isolamento:** serviços e clientes em `lib/server/`, tipos em `lib/types/`, interface apenas em `routes/` + `components/`.

## Referências

- [ADR-001: Escolha da Stack](../decisions/ADR-001-escolha-da-stack.md)
- [ADR-002: Fonte de Dados Oficial do CNPJ](../decisions/ADR-002-fonte-de-dados-open-cnpj.md)
- [ADR-003: Estratégia de Enriquecimento DuckDuckGo](../decisions/ADR-003-estrategia-de-enriquecimento-duckduckgo.md)
