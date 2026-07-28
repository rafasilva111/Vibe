# Dashboard

## Descrição
Dashboard configurável para visualização de métricas e KPIs.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome do dashboard |
| proprietario_id | UUID (FK) | Criador |
| configuracao | JSON | Layout e widgets |
| publico | Boolean | Se é público |
| criado_em | Datetime | Data de criação |
