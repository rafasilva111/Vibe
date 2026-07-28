# Plataforma — Auditoria

## Propósito

Disponibilizar o registo imutável e auditável de todas as acções relevantes na Junta Observatory Platform, garantindo a rastreabilidade e conformidade regulatória.

## Responsabilidades

- Registar todas as acções com impacto legal ou operacional
- Garantir a imutabilidade dos logs de auditoria
- Disponibilizar consulta e exportação para entidades externas
- Integrar com SIEM para análise de segurança

## Descrição Detalhada

### Eventos Auditáveis

| Categoria | Eventos | Retenção |
|---|---|---|
| **Autenticação** | Login, logout, falha de autenticação, refresh de token | 2 anos |
| **Casos** | Criação, alteração de estado, despacho, notificação | 10 anos |
| **Documentos** | Upload, download, eliminação, assinatura | 10 anos |
| **Utilizadores** | Criação, alteração de permissões, suspensão | 5 anos |
| **Dados Pessoais** | Acesso, exportação, rectificação, eliminação | 10 anos |
| **Administração** | Alteração de configurações, manutenção | 5 anos |
| **Integrações** | Chamadas a APIs externas, webhooks | 2 anos |

### Estrutura do Log

| Campo | Descrição | Exemplo |
|---|---|---|
| `eventId` | Identificador único | `evt_abc123` |
| `timestamp` | Data/hora (UTC) | `2024-06-15T10:30:00Z` |
| `actor` | Quem executou | `user_42` ou `system` |
| `tenantId` | Inquilino | `junta_xyz` |
| `action` | Acção executada | `caso.criar` |
| `resourceType` | Tipo de recurso | `Caso` |
| `resourceId` | ID do recurso | `caso_789` |
| `details` | Detalhes (JSON) | `{"estado": "Pendente"}` |
| `ipAddress` | Endereço IP | `10.0.1.42` |
| `traceId` | Correlation ID | `trace_abc` |

## Documentos Relacionados

- [03 — Event Sourcing](../03-arquitetura/event-sourcing.md)
- [08 — Observabilidade](../08-observabilidade/index.md)
- [13 — RGPD](../13-governanca-conformidade/rgpd.md)
