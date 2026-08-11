# Search CNPJs

Sistema de busca de CNPJ na API **Open CNPJ** com enriquecimento de dados coletados da web sobre a empresa consultada.

Este projeto faz parte de uma sequência de projetos de portfólio de desenvolvimento com IA. Aqui, a inteligência artificial executa e estrutura o código técnico, enquanto o desenvolvedor **Joaby** atua como piloto humano: planejando, tomando as decisões de design e regras de negócio, e testando manualmente o resultado.

## 🎯 Objetivo

Permitir que o usuário consulte um CNPJ válido e receba, em um único lugar:

- Os dados oficiais da empresa fornecidos pela API Open CNPJ.
- Informações complementares (enriquecimento) obtidas de fontes da web sobre esse CNPJ.

## 🛠️ Stack Tecnológica

- **Framework:** SvelteKit (Svelte 5) com Server-Side Rendering (SSR)
- **Linguagem:** TypeScript
- **Interface:** HTML e CSS
- **Integração de Dados:** API Open CNPJ + enriquecimento com dados da web
- **Hospedagem:** Vercel (deploy contínuo a partir da branch `main`, runtime `nodejs22.x`)

## 🚀 Execução

Este projeto **nunca é executado ou instalado localmente**. O código é versionado no GitHub e roda exclusivamente na hospedagem da **Vercel**, onde os builds e testes de execução acontecem automaticamente via deploy contínuo a partir da branch `main`.

## 🧠 Divisão de Papéis

Este projeto é desenvolvido em parceria humano + IA:

| Papel | Responsável | Atividades |
|---|---|---|
| **Arquiteto / Piloto** | Joaby | Planejamento, decisões de design, regras de negócio, testes manuais |
| **Executor** | IA | Estruturação e escrita do código técnico |

Joaby **não escreve código** neste projeto: ele guia a IA na tomada de decisões e valida o resultado por meio de testes.

## 📂 Estrutura do Repositório

- `tasks/` — memória operacional (checklists atômicas de execução)
- `decisions/` — memória histórica (ADRs e decisões tomadas)
- `architecture/` — memória arquitetural (visão do sistema)
- `agents/skills/` — memória especializada (lições aprendidas, erros recorrentes)
- `playbooks/` — memória procedimental (rotinas de deploy, teste e operação)
