# Métrica

## Descrição
Métrica técnica ou de negócio recolhida pelo sistema.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome da métrica |
| valor | Decimal | Valor |
| etiquetas | JSON | Tags/labels |
| intervalo | Enum | 1min, 5min, 1h, 1d |
| timestamp | Datetime | Momento da recolha |
