# Módulo 04 — Enriquecimento Web (DuckDuckGo)

Status: ⏳ Pendente

## Objetivo
Implementar o serviço e cliente HTTP para busca de dados complementares no DuckDuckGo (HTML) com degradação graciosa em caso de bloqueio ou indisponibilidade, conforme ADR-003.

## Checklist de Tarefas
- [ ] Implementar `src/lib/server/clients/duckduckgo.client.ts` para requisição na versão HTML (`html.duckduckgo.com/html/`).
- [ ] Implementar parser leve de HTML para extração de títulos, links e snippets dos resultados relevantes.
- [ ] Implementar `src/lib/server/services/enrichment.service.ts` para cruzar dados oficiais (razão social, município, sócios) e montar queries inteligentes.
- [ ] Implementar degradação graciosa: garantir que falhas no DuckDuckGo nunca quebrem a exibição dos dados oficiais da Open CNPJ.
- [ ] Respeitar User-Agent realista e tratamento de rate limits/bloqueios.
