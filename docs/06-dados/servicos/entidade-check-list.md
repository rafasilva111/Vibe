# Check List

## Descrição
Checklist de verificação associada a um serviço ou tarefa.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| servico_id | UUID (FK) | Serviço associado |
| nome | String | Nome da checklist |
| obrigatoria | Boolean | Se é de cumprimento obrigatório |
