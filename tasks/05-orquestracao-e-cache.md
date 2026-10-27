# Módulo 05 — Orquestração e Cache

Status: ⏳ Pendente

## Objetivo
Implementar o serviço central de orquestração do fluxo de busca (validação, consulta de CNPJ, enriquecimento) com mecanismo de cache em memória para otimização de requisições.

## Checklist de Tarefas
- [ ] Implementar mecanismo leve de cache em memória com TTL (Time-To-Live) em `src/lib/server/cache/memory-cache.ts`.
- [ ] Implementar serviço de orquestração `src/lib/server/services/cnpj-search.service.ts`.
- [ ] Integrar fluxo sequencial: verificar cache -> validar CNPJ -> consultar Open CNPJ -> enriquecer via DuckDuckGo -> armazenar em cache -> retornar resultado consolidado.
- [ ] Tratar cenários de erro e respostas estruturadas para a rota SSR.
