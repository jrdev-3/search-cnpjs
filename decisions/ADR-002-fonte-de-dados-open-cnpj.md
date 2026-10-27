# ADR-002: Fonte de Dados Oficial do CNPJ — API Open CNPJ

## Status
Aceito

## Contexto
O sistema precisa consultar dados oficiais de um CNPJ informado pelo usuário. Existem fontes públicas (Receita Federal, BrasilAPI) e fontes privadas com custo. A fonte precisa ser gratuita, sem necessidade de chave de API e com contrato claro de dados.

## Decisão
Utilizar a **API Open CNPJ** (`https://api.opencnpj.org/{cnpj}`) mantida pelo projeto open source **OpenCNPJ** (`https://opencnpj.org`) como fonte oficial de dados do CNPJ.

O contrato da API Open CNPJ (`https://api.opencnpj.org/schema`) é a **fonte da verdade de tipos** para o shape dos dados do CNPJ em TypeScript.

## Consequências
- A integração fica isolada em um cliente dedicado em `src/lib/`, sem vazar para as rotas ou para a interface.
- Os tipos TypeScript são derivados do contrato da API, garantindo consistência no build.
- Consultas são feitas no servidor (SSR), protegendo a chamada e permitindo tratar erros (CNPJ inválido, 404, timeout).

## Alternativas consideradas
- **BrasilAPI:** descartada por possuir limite de requisições e cobertura de dados menor para o propósito do projeto.
- **Receita Federal direta:** descartada por exigir captcha/validações e ter formato menos amigável.
- **APIs pagas:** descartadas por incompatibilidade com o objetivo de portfólio gratuito.
