# Versão Workflow

## Descrição
Versão específica de um workflow.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| workflow_id | UUID (FK) | Workflow associado |
| versao | String | Versão semântica |
| definicao | JSON | Definição completa do workflow |
| estado | Enum | Rascunho, Activo, Substituido |
| criado_em | Datetime | Data de criação |
