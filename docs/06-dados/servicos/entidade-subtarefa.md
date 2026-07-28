# Subtarefa

## Descrição
Subtarefa dentro de uma tarefa maior.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| tarefa_id | UUID (FK) | Tarefa associada |
| titulo | String | Título |
| concluida | Boolean | Estado de conclusão |
| concluido_em | Datetime | Data de conclusão |
