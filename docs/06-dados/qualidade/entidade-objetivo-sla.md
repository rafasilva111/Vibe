# Objetivo SLA

## Descrição
Objetivo específico dentro de um SLA.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| sla_id | UUID (FK) | SLA associado |
| metrica | String | Métrica monitorizada |
| alvo | Decimal | Valor alvo |
| tolerancia | Decimal | Tolerância permitida |
