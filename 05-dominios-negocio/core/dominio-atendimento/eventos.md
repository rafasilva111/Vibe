# Atendimento — Eventos

## Eventos de Domínio

| Evento | Significado | Consumidores |
|---|---|---|
| `atendimento.checkin.realizado` | Cidadão fez check-in | Filas, Dashboards |
| `atendimento.iniciado` | Atendimento começou | Auditoria, Métricas |
| `atendimento.concluido` | Atendimento terminou | Casos, Feedback |
| `atendimento.agendamento.criado` | Novo agendamento | Notificações, Agenda |
| `atendimento.reclamacao.registada` | Reclamação registada | Processos, Qualidade |

## Documentos Relacionados

- [04 — Eventos](../../../04-servicos-plataforma/plataforma-eventos.md)
- [03 — Event Sourcing](../../../03-arquitetura/event-sourcing.md)
