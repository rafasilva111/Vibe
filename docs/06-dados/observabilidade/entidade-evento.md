# Evento

## Descrição
Evento de domínio registado no event store.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| tipo | String | Tipo do evento (ex: caso.criado) |
| agregado_id | UUID | ID do agregado |
| agregado_tipo | String | Tipo do agregado |
| dados | JSON | Payload do evento |
| metadados | JSON | Metadados (traceId, userId) |
| versao | Integer | Versão do agregado |
| ocorrido_em | Datetime | Timestamp |
