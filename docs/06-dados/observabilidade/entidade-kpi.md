# KPI

## Descrição
Indicador-chave de desempenho.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome do KPI |
| descricao | String | Descrição |
| formula | String | Fórmula de cálculo |
| periodicidade | Enum | Diária, Semanal, Mensal, Trimestral |
| unidade | String | Unidade de medida |
| alerta_limite | Decimal | Limite para alerta |
