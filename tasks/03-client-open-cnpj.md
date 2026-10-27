# Módulo 03 — Cliente API Open CNPJ

Status: ⏳ Pendente

## Objetivo
Implementar o cliente HTTP isolado do lado do servidor para consultar dados oficiais de empresas na API Open CNPJ com tratamento resiliente de erros.

## Checklist de Tarefas
- [ ] Implementar `src/lib/server/clients/open-cnpj.client.ts`.
- [ ] Configurar chamada GET para `https://api.cnpjs.dev/v1/cnpj/{cnpj}` com timeout seguro e headers adequados.
- [ ] Mapear respostas de sucesso (200) para o tipo do contrato de domínio.
- [ ] Mapear e tratar erros da API: 404 (CNPJ não encontrado), 429 (rate limit), 5xx (indisponibilidade da API externa).
- [ ] Garantir execução exclusiva no ambiente do servidor (`$lib/server`).
