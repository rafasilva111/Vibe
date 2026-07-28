# Passo

## Descrição
Passo individual dentro de um workflow.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| workflow_id | UUID (FK) | Workflow associado |
| nome | String | Nome do passo |
| tipo | Enum | Automático, Tarefa, Decisão |
| ordem | Integer | Ordem no workflow |
| configuracao | JSON | Configuração específica do passo |
