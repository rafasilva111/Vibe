# Modelo de Eventos

## Propósito
Definir o modelo de eventos para observabilidade.

## Estrutura

| Campo | Descrição |
|---|---|
| `id` | Identificador único do evento |
| `type` | Tipo do evento |
| `source` | Serviço de origem |
| `timestamp` | Timestamp ISO 8601 |
| `data` | Payload do evento |
| `traceId` | Trace ID para correlação |
| `userId` | Utilizador (se aplicável) |
| `tenantId` | Inquilino |

## Tipos de Evento

| Tipo | Descrição |
|---|---|
| `request.started` | Request HTTP iniciado |
| `request.completed` | Request HTTP concluído |
| `request.failed` | Request HTTP falhou |
| `db.query` | Query à base de dados |
| `kafka.produce` | Mensagem publicada no Kafka |
| `kafka.consume` | Mensagem consumida do Kafka |
| `cache.hit` | Cache hit |
| `cache.miss` | Cache miss |
