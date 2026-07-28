# Plataforma — API

## Propósito

Definir a camada de API exposta pela Junta Observatory Platform, incluindo a API pública para parceiros/integradores e a API interna para o frontend.

## Responsabilidades

- Expor endpoints REST/GraphQL para acesso aos recursos
- Gerir autenticação e autorização por endpoint
- Documentar contratos (OpenAPI 3.0)
- Controlar versões e deprecação

## Descrição Detalhada

### API Gateway

| Aspecto | Detalhe |
|---|---|
| **Gateway** | Kong / AWS API Gateway |
| **Protocolo** | HTTPS (TLS 1.3) |
| **Formato** | JSON (REST) + GraphQL (queries complexas) |
| **Autenticação** | JWT (OIDC), API Keys (serviços) |
| **Rate Limiting** | 100 req/s por tenant (configurável) |
| **Versionamento** | URI path (`/api/v1/`) |

### Categorias de Endpoints

| Categoria | Exemplos | Público |
|---|---|---|
| **Catálogo** | `GET /servicos`, `GET /servicos/{id}` | Sim |
| **Casos** | `POST /casos`, `GET /casos/{id}` | Sim (autenticado) |
| **Documentos** | `POST /documentos`, `GET /documentos/{id}` | Sim (autenticado) |
| **Tarefas** | `GET /tarefas`, `PATCH /tarefas/{id}` | Funcionários |
| **Workflows** | `POST /workflows/instancias` | Interno |
| **Administração** | `GET /admin/tenants` | Admin |
| **Integração** | `POST /webhooks`, `GET /eventos` | Parceiros |

## Documentos Relacionados

- [03 — API Gateway](../03-arquitetura/api-gateway.md)
- [10 — Integrações](../10-integracoes/index.md)
- [12 — Documentação API](../12-desenvolvimento/documentacao-api.md)
