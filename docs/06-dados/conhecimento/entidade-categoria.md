# Categoria

## Descrição
Categoria para organização da base de conhecimento.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome da categoria |
| descricao | String | Descrição |
| categoria_pai_id | UUID (FK) | Categoria superior |
