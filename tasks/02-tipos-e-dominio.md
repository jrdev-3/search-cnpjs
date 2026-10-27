# Módulo 02 — Tipos e Validação de Domínio

Status: ⏳ Pendente

## Objetivo
Definir os contratos de tipos TypeScript baseados no schema oficial da API Open CNPJ (`https://api.opencnpj.org/schema`) e a lógica de validação de CNPJ (dígitos verificadores padrão e suporte alfanumérico) no domínio isolado.

## Checklist de Tarefas
- [ ] Definir o contrato TypeScript de resposta da API Open CNPJ em `src/lib/types/cnpj.ts` com base no schema oficial:
  - Dados cadastrais (`cnpj`, `razao_social`, `nome_fantasia`, `situacao_cadastral`, `data_situacao_cadastral`, `matriz_filial`, `data_inicio_atividade`, `porte_empresa`).
  - Atividades econômicas (`cnae_principal`, `cnaes_secundarios`).
  - Natureza jurídica (`codigo_natureza_juridica`, `natureza_juridica`).
  - Localização e contato (`tipo_logradouro`, `logradouro`, `numero`, `complemento`, `bairro`, `cep`, `uf`, `municipio`, `email`, `telefones`).
  - Regime e capital (`capital_social`, `opcao_simples`, `data_opcao_simples`, `opcao_mei`, `data_opcao_mei`).
  - Quadro societário (`QSA`) e metadados (`updated_at`).
- [ ] Definir o modelo de dados de enriquecimento e do resultado consolidado em `src/lib/types/enrichment.ts` e `src/lib/types/search-result.ts`.
- [ ] Implementar utilitário de validação de CNPJ em `src/lib/domain/cnpj-validator.ts` (validação de tamanho de 14 dígitos/caracteres, regex alfanumérico `^[A-Z0-9]{12}\d{2}$` e cálculo dos 2 dígitos verificadores).
- [ ] Implementar formatador/higienizador de CNPJ em `src/lib/domain/cnpj-formatter.ts` (remoção de máscara para busca e formatação canônica `XX.XXX.XXX/XXXX-XX`).
- [ ] Garantir tipagem segura, sem uso de `any` e com nomenclatura estritamente em inglês.

