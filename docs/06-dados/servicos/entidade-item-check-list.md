# Item Check List

## Descrição
Item individual de uma checklist de verificação.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| check_list_id | UUID (FK) | Checklist associada |
| descricao | String | Descrição do item |
| ordem | Integer | Ordem de apresentação |
| obrigatorio | Boolean | Se é obrigatório |
