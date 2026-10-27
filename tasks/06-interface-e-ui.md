# Módulo 06 — Interface e UI de Busca

Status: ⏳ Pendente

## Objetivo
Construir a interface do usuário (HTML e CSS vanilla moderno, sem Tailwind) com Svelte 5 (Runes), foco em experiência premium, máscara de digitação, feedback de carregamento e exibição elegante dos dados oficiais e enriquecidos.

## Checklist de Tarefas
- [ ] Criar design system base e tokens visuais em `src/app.css` (cores refinadas, tipografia moderna, layout responsivo).
- [ ] Implementar rota de orquestração SSR em `src/routes/+page.server.ts` (carregamento e ações de busca).
- [ ] Criar componente de entrada de busca com máscara dinâmica de CNPJ (`##.###.###/####-##`) e validação visual em tempo real.
- [ ] Criar componente de exibição dos dados oficiais da empresa (`src/lib/components/CnpjDetails.svelte`).
- [ ] Criar componente de exibição dos dados de enriquecimento web (`src/lib/components/EnrichmentSection.svelte`) com badge de status / disponibilidade.
- [ ] Implementar tratamento visual para estados: inicial, carregando, sucesso, erro de validação e empresa não encontrada (404).
