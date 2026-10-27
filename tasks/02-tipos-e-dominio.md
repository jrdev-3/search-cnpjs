# Módulo 02 — Tipos e Validação de Domínio

Status: ⏳ Pendente

## Objetivo
Definir os contratos de tipos TypeScript baseados na API Open CNPJ e a lógica de validação de CNPJ puro (dígitos verificadores e formatação) no domínio isolado.

## Checklist de Tarefas
- [ ] Definir o shape do retorno da API Open CNPJ em `src/lib/types/cnpj.ts` (razão social, nome fantasia, CNAEs, quadro societário, status, endereço, contatos).
- [ ] Definir o modelo de dados de enriquecimento e do resultado consolidado em `src/lib/types/enrichment.ts` e `src/lib/types/search-result.ts`.
- [ ] Implementar utilitário de validação matemática de dígitos verificadores de CNPJ em `src/lib/domain/cnpj-validator.ts`.
- [ ] Implementar formatador/higienizador de máscara de CNPJ em `src/lib/domain/cnpj-formatter.ts`.
- [ ] Garantir tipagem segura, sem uso de `any` e com nomenclatura estritamente em inglês.
