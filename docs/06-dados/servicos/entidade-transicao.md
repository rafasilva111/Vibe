# Transição

## Descrição
Transição entre estados num workflow.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| workflow_id | UUID (FK) | Workflow associado |
| de_estado | String | Estado de origem |
| para_estado | String | Estado de destino |
| nome | String | Nome da transição |
| condicao | String | Condição para activação (expressão) |
