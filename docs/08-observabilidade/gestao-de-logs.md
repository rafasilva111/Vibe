# Gestão de Logs

## Propósito
Definir a estratégia de gestão de logs da Junta Observatory Platform.

## Níveis

| Nível | Descrição | Acção |
|---|---|---|
| `ERROR` | Erro que requer intervenção | Alerta imediato |
| `WARN` | Situação anómala não crítica | Revisão diária |
| `INFO` | Informação operacional | Armazenar |
| `DEBUG` | Detalhe para debugging | Desligado em produção |

## Estrutura

Todos os logs seguem formato estruturado (JSON):

```json
{
  "timestamp": "2024-06-15T10:30:00Z",
  "level": "INFO",
  "service": "workflow-engine",
  "traceId": "trace-abc-123",
  "message": "Caso criado",
  "data": { "casoId": "caso_789" }
}
```

## Retenção

| Ambiente | Retenção | Armazenamento |
|---|---|---|
| Produção | 30 dias (quentes), 1 ano (frios) | Loki + S3 |
| Staging | 7 dias | Loki |
| Desenvolvimento | 3 dias | Console |
