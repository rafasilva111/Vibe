# Webhooks

## Propósito
Definir o sistema de webhooks para notificações a sistemas externos.

## Formato

```json
{
  "event": "caso.transicionado",
  "timestamp": "2024-06-15T10:30:00Z",
  "tenantId": "junta_xyz",
  "data": {
    "casoId": "caso_789",
    "estado": "Decidido",
    "servico": "Licença de Obra"
  }
}
```

## Configuração

| Parâmetro | Descrição |
|---|---|
| URL | Endpoint de destino |
| Eventos | Lista de eventos a enviar |
| Segredo | HMAC secret para assinatura |
| Retry | 3 tentativas com backoff exponencial |
| Timeout | 10s |

## Segurança

- Payload assinado com HMAC-SHA256
- Header `X-Signature: <hmac>`
- Verificação de IP (whitelist)
- Timeout e retry com backoff

## Documentos Relacionados

- [04 — Eventos](../04-servicos-plataforma/plataforma-eventos.md)
