# Plataforma — Dashboards

## Propósito

Disponibilizar dashboards interactivos para monitorização e análise da operação da Junta Observatory Platform, adaptados a cada perfil de utilizador.

## Responsabilidades

- Exibir KPIs operacionais em tempo real
- Disponibilizar visualizações de process mining
- Permitir criação de dashboards personalizados
- Exportar dados para ferramentas externas (Power BI, Tableau)

## Descrição Detalhada

### Dashboards por Perfil

| Perfil | KPIs Principais |
|---|---|
| **Cidadão** | Estado dos meus processos, próximos prazos |
| **Funcionário** | Tarefas pendentes, carga de trabalho, prazos críticos |
| **Dirigente** | Indicadores de desempenho, tempo médio por serviço |
| **Administrador** | Utilizadores activos, armazenamento, performance do sistema |

### KPIs Operacionais

| KPI | Fonte | Actualização |
|---|---|---|
| Processos em aberto | Event Store | 5 min |
| Tempo médio de resposta | Workflow Engine | 15 min |
| Taxa de cumprimento de prazos | Workflow Engine | Diária |
| Documentos pendentes | Document Service | 5 min |
| Tarefas por técnico | Task Service | 5 min |
| Satisfação do cidadão | Feedback Service | Mensal |

## Documentos Relacionados

- [08 — Observabilidade](../08-observabilidade/index.md)
- [08 — Process Mining](../08-observabilidade/process-mining.md)
- [09 — BI / Analytics](../09-inteligencia-artificial/index.md)
