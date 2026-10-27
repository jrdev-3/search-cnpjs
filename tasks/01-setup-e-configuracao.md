# Módulo 01 — Setup & Configuração

Status: ⏳ Pendente

## Objetivo
Estruturar o esqueleto do projeto SvelteKit com Svelte 5, TypeScript, SSR e adaptador Vercel, pronto para compilação remota (sem instalação local).

## Checklist de Tarefas
- [ ] Criar `package.json` com scripts de build e dependências essenciais (`@sveltejs/kit`, `@sveltejs/adapter-vercel`, `svelte`, `typescript`, `vite`).
- [ ] Criar `svelte.config.js` configurado com `@sveltejs/adapter-vercel` e target Node 22.
- [ ] Criar `vite.config.ts` com plugin `@sveltejs/kit/vite`.
- [ ] Criar `tsconfig.json` com suporte a SvelteKit e tipagem estrita TypeScript.
- [ ] Criar arquivo raiz de template HTML `src/app.html`.
- [ ] Criar arquivo de declaração de tipos ambientais `src/app.d.ts`.
- [ ] Criar estrutura inicial de layout `src/routes/+layout.svelte` e estilos globais `src/app.css`.
- [ ] Validar conformidade das configurações com deploy automático na Vercel.
