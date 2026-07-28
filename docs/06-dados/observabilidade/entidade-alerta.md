# Alerta

## Descrição
Alerta configurado para notificar quando um limiar é atingido.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome do alerta |
| metrica_id | UUID (FK) | Métrica monitorizada |
| condicao | Enum | >, <, >=, <=, == |
| limiar | Decimal | Valor limiar |
| gravidade | Enum | Info, Warning, Critical |
| destino | JSON | Canais de notificação |
| activo | Boolean | Se está activo |
