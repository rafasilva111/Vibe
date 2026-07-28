# Alertas

## Propósito
Definir o sistema de alertas da Junta Observatory Platform.

## Tipos

| Tipo | Descrição | Canais |
|---|---|---|
| **Técnico** | Falha de infraestrutura | Email, PagerDuty |
| **SLA** | Risco de incumprimento | Email, Dashboard |
| **Negócio** | Anomalia em KPIs | Email, Dashboard |
| **Segurança** | Tentativa de acesso suspeita | Email, SIEM |

## Regras

| Alerta | Condição | Gravidade |
|---|---|---|
| **Serviço Down** | Health check falha > 3x | Crítico |
| **Latência Alta** | p95 > 1s por 5 min | Crítico |
| **Erro Alto** | Error rate > 5% | Crítico |
| **Prazo Expirado** | Processo excedeu prazo | Alto |
| **SLA Risco** | 80% do prazo decorrido | Médio |
| **Disco Cheio** | Uso > 85% | Alto |
