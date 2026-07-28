# Feature Flag

## Descrição
Funcionalidade activável/desactivável por inquilino.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome da feature |
| descricao | String | Descrição |
| activa | Boolean | Estado global |
| regras | JSON | Regras por inquilino/grupo |
