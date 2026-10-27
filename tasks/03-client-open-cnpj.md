# Módulo 03 — Cliente API Open CNPJ

Status: ⏳ Pendente

## Objetivo
Implementar o cliente HTTP isolado do lado do servidor para consultar dados oficiais de empresas na API Open CNPJ (`https://api.opencnpj.org/{cnpj}`) com suporte ao contrato oficial, CNPJs numéricos e alfanuméricos, e tratamento resiliente de erros.

## Checklist de Tarefas
- [ ] Implementar `src/lib/server/clients/open-cnpj.client.ts`.
- [ ] Configurar chamada GET para `https://api.opencnpj.org/{cnpj}` com timeout seguro, User-Agent explícito e headers adequados.
- [ ] Suportar consulta tanto por CNPJ normalizado (14 dígitos/caracteres) quanto com máscara.
- [ ] Mapear respostas de sucesso (200) para o tipo do contrato de domínio baseado no schema oficial (`https://api.opencnpj.org/schema`).
- [ ] Mapear e tratar erros da API: 400 (CNPJ inválido), 404 (CNPJ não encontrado), 429 (rate limit) e 502/5xx (indisponibilidade ou erro de payload).
- [ ] Garantir execução exclusiva no ambiente do servidor (`$lib/server`).

