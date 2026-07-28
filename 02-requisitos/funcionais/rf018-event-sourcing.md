# RF-018 — Event Sourcing

## Propósito

Implementar um modelo de persistência baseado em eventos imutáveis para o motor de processos, garantindo rastreabilidade total, capacidade de auditoria e reconstrução do estado em qualquer ponto do tempo.

## Descrição

O Event Sourcing armazena cada alteração de estado como um evento imutável num event store dedicado. O estado actual de cada processo é derivado por projecção dos eventos. Os eventos são a fonte única de verdade (source of truth) para o motor de processos, enquanto os dados de referência (catálogo, utilizadores) usam base de dados relacional tradicional (modelo híbrido).

## Requisitos

| ID | Requisito | Prioridade |
|---|---|---|
| RF-018.01 | O sistema deve armazenar todos os eventos de domínio como registos imutáveis (append-only) | Alta |
| RF-018.02 | O event store deve garantir que eventos não podem ser alterados ou eliminados | Alta |
| RF-018.03 | O sistema deve permitir reconstruir o estado de qualquer processo a partir dos eventos | Alta |
| RF-018.04 | O sistema deve suportar projecções (read models) para consultas eficientes | Alta |
| RF-018.05 | O sistema deve permitir fazer replay de eventos para recovery ou auditoria | Alta |
| RF-018.06 | O sistema deve suportar snapshots para optimizar a reconstrução de estados longos | Média |
| RF-018.07 | O sistema deve publicar eventos num message broker para consumo por outros serviços | Alta |
| RF-018.08 | O sistema deve garantir a ordenação total dos eventos por agregado | Alta |
| RF-018.09 | O sistema deve suportar event versioning (evolução do schema de eventos) | Alta |
| RF-018.10 | O sistema deve expor uma API de consulta de eventos por agregado, tipo e período | Média |

## Critérios de Aceitação

- O replay de 100.000 eventos para um agregado demora menos de 5 segundos
- Snapshots reduzem o tempo de reconstrução em pelo menos 80%
- Eventos não podem ser alterados após escrita (verificado por teste de integridade)
- A ordenação de eventos por agregado é consistente e verificável
- Novas versões de eventos são compatíveis com leitores antigos (forward compatibility)

## Regras de Negócio

- Eventos de domínio seguem o formato CloudEvents para interoperabilidade
- Cada evento inclui: id, tipo, timestamp, agregado_id, versão, dados, metadados
- Eventos de erro (compensação) seguem o padrão Saga para transacções distribuídas
- O schema de eventos evolui com versionamento semântico (major.minor)

## Métricas

- Número de eventos armazenados por mês
- Taxa de ingestão de eventos (eventos/segundo)
- Tempo médio de reconstrução de estado por snapshots vs replay total
- Percentagem de eventos com schema da versão actual

## Documentos Relacionados

- [RF-002 — Motor de Workflows](rf002-motor-de-workflows.md)
- [RF-017 — Auditoria](rf017-auditoria.md)
- [03 — Arquitectura / Event Sourcing](../../03-arquitetura/event-sourcing.md)
- [03 — Arquitectura / CQRS](../../03-arquitetura/cqrs.md)
- [08 — Observabilidade / Modelo de Eventos](../../08-observabilidade/modelo-de-eventos.md)
