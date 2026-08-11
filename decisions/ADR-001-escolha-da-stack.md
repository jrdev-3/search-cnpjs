# ADR-001: Escolha da Stack Tecnológica

## Status
Aceito

## Contexto
O projeto Search CNPJs faz parte de uma sequência de projetos de portfólio de desenvolvimento com IA. O objetivo é criar um sistema de busca de CNPJ na API Open CNPJ com enriquecimento de dados da web. O desenvolvedor (Joaby) atua como piloto humano e não escreve código; a IA é responsável pela execução técnica.

Para o portfólio, a stack precisa ser moderna, demonstrar SSR e boas práticas de TypeScript, e ter deploy simples e contínuo.

## Decisão
Utilizar:

- **Framework:** SvelteKit (Svelte 5) com Server-Side Rendering (SSR)
- **Linguagem:** TypeScript
- **Interface:** HTML e CSS (sem frameworks de UI)
- **Hospedagem:** Vercel (deploy contínuo a partir da branch `main`, runtime `nodejs22.x`)

## Consequências
- SSR permite buscar os dados da API Open CNPJ e fazer o enriquecimento no servidor, evitando expor lógica e reduzindo chamadas a partir do navegador.
- O runtime `nodejs22.x` deve estar alinhado entre `package.json` (`engines`) e o adapter da Vercel.
- O projeto não é executado localmente: builds e testes de execução acontecem exclusivamente na Vercel.
- Svelte 5 exige cuidado com compatibilidade de bibliotecas (ver skills em `agents/skills/`).

## Alternativas consideradas
- **Next.js/React:** descartado por divergir do padrão da sequência de portfólio (SvelteKit).
- **Astro:** descartado por focar em conteúdo estático, enquanto o projeto tem interação dinâmica.
