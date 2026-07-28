# SLA

## Descrição
Acordo de nível de serviço para um serviço.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| servico_id | UUID (FK) | Serviço associado |
| prazo_horas | Integer | Prazo em horas úteis |
| prioridade | Enum | Baixa, Normal, Alta, Crítica |
| penalidade | String | Penalidade por incumprimento |
