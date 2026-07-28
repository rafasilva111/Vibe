# Domínio — Gestão de Processos

## Propósito

Gerir o ciclo de vida dos processos administrativos na Junta Observatory Platform, desde a abertura até ao arquivo, incluindo a execução de workflows, tarefas, prazos e regras de negócio.

## Entidades Principais

| Entidade | Descrição |
|---|---|
| **Caso** | Processo administrativo |
| **WorkflowInstance** | Instância em execução de um workflow |
| **Task** | Tarefa atribuída a um utilizador |
| **Timeline** | Linha temporal de eventos do processo |
| **Prazo** | Prazo legal ou interno associado |
| **AuditTrail** | Registo de auditoria do processo |

## Regras de Negócio

- Cada processo segue o workflow definido no catálogo do serviço
- Prazos legais são calculados em dias úteis (CPA)
- Transições de estado são registadas no event store
- A reabertura de processo arquivado requer autorização do dirigente
- Processos com dados pessoais são pseudonimizados após arquivo
