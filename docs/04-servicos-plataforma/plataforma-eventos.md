# Plataforma — Eventos

## Propósito

Gerir o barramento de eventos da Junta Observatory Platform, suportando a publicação, subscrição e encaminhamento de eventos entre domínios e serviços.

## Responsabilidades

- Publicar eventos de domínio no barramento (Kafka)
- Gerir subscrições por serviço
- Garantir a entrega fiável (pelo menos uma vez)
- Suportar replay de eventos

## Descrição Detalhada

### Categorias de Eventos

| Categoria | Exemplos | Consumidores |
|---|---|---|
| **caso** | `caso.criado`, `caso.transicionado`, `caso.decidido` | Workflow, Notificações, Process Mining |
| **documento** | `documento.uploaded`, `documento.assinado` | Casos, Índice |
| **utilizador** | `utilizador.registado`, `utilizador.eliminado` | Auditoria, Notificações |
| **tarefa** | `tarefa.atribuida`, `tarefa.concluida` | Workflow, Dashboards |
| **notificacao** | `notificacao.enviada`, `notificacao.falhou` | Auditoria |
| **sistema** | `tenant.criado`, `manutencao.agendada` | Administração |

### Schema Registry

Todos os eventos seguem um schema definido no Schema Registry (Avro/Protobuf), garantindo compatibilidade entre produtores e consumidores.

## Documentos Relacionados

- [03 — Event Sourcing](../03-arquitetura/event-sourcing.md)
- [03 — Comunicação entre Serviços](../03-arquitetura/comunicacao-entre-servicos.md)
- [03 — CQRS](../03-arquitetura/cqrs.md)
