# Gestão de Processos — Eventos

## Eventos de Domínio

| Evento | Significado | Consumidores |
|---|---|---|
| `caso.criado` | Novo processo administrativo | Workflow, Catálogo |
| `caso.transicionado` | Mudança de estado do processo | Workflow, Dashboards |
| `caso.decidido` | Decisão proferida | Documentos, Notificações |
| `caso.notificado` | Cidadão notificado da decisão | Casos |
| `caso.arquivado` | Processo arquivado | Arquivo, Métricas |
| `caso.reaberto` | Processo reaberto | Workflow |

## Documentos Relacionados

- [04 — Eventos](../../../04-servicos-plataforma/plataforma-eventos.md)
- [03 — Event Sourcing](../../../03-arquitetura/event-sourcing.md)
