# Índice de Tarefas — Search CNPJs

Este documento rastreia o progresso geral e a execução atômica de cada módulo do sistema **Search CNPJs**, em conformidade com as diretrizes do [AGENTS.md](../AGENTS.md) e a arquitetura definida em [overview.md](../architecture/overview.md).

---

## 📌 Status Geral dos Módulos

| Módulo | Arquivo de Checklist | Status | Descrição |
|---|---|---|---|
| **01. Setup & Configuração** | [01-setup-e-configuracao.md](01-setup-e-configuracao.md) | ⏳ Pendente | Estrutura base SvelteKit 5, TypeScript, SSR e deploy Vercel |
| **02. Tipos e Validação de Domínio** | [02-tipos-e-dominio.md](02-tipos-e-dominio.md) | ⏳ Pendente | Contrato de tipos Open CNPJ e validação matemática de CNPJ |
| **03. Cliente API Open CNPJ** | [03-client-open-cnpj.md](03-client-open-cnpj.md) | ⏳ Pendente | Integração HTTP resiliente com a API pública de CNPJs |
| **04. Enriquecimento Web (DuckDuckGo)** | [04-enriquecimento-duckduckgo.md](04-enriquecimento-duckduckgo.md) | ⏳ Pendente | Crawler/parser leve DuckDuckGo HTML com degradação graciosa |
| **05. Orquestração e Cache** | [05-orquestracao-e-cache.md](05-orquestracao-e-cache.md) | ⏳ Pendente | Serviço de busca integrado com camada de cache em memória |
| **06. Interface e UI de Busca** | [06-interface-e-ui.md](06-interface-e-ui.md) | ⏳ Pendente | Página de busca, máscara de CNPJ, feedback de loading e resultados |
| **07. Playbooks e Documentação Final** | [07-playbooks-e-fechamento.md](07-playbooks-e-fechamento.md) | ⏳ Pendente | Playbooks operacionais, rotinas de verificação e checklist de deploy |

---

## 🧭 Legenda de Status
- ⏳ **Pendente:** Não iniciado.
- 🚧 **Em Progresso:** Tarefa ativa no momento.
- ✅ **Concluído:** Finalizado, validado e com commit atômico realizado.
