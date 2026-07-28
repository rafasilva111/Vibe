# RF-020 — API Pública

## Propósito

Expor uma API pública RESTful que permita a integração da Junta Observatory Platform com sistemas externos, parceiros e o ecossistema nacional de administração pública.

## Descrição

A API Pública segue os princípios REST, utiliza JSON como formato de dados e suporta autenticação via OAuth 2.0 / OpenID Connect. É versionada semanticamente e documentada segundo a especificação OpenAPI 3.1.

## Requisitos

| ID | Requisito | Prioridade |
|---|---|---|
| RF-020.01 | A API deve expor endpoints para: catálogo de serviços, processos, documentos, notificações | Alta |
| RF-020.02 | A API deve suportar operações CRUD para recursos autorizados | Alta |
| RF-020.03 | A API deve suportar paginação, ordenação e filtros em listagens | Alta |
| RF-020.04 | A API deve utilizar OAuth 2.0 com fluxos client_credentials e authorization_code | Alta |
| RF-020.05 | A API deve ser versionada (prefixo /v1/, /v2/) | Alta |
| RF-020.06 | A API deve seguir a especificação OpenAPI 3.1 com documentação interactiva (Swagger UI) | Alta |
| RF-020.07 | A API deve limitar taxa de requisições (rate limiting) por cliente | Alta |
| RF-020.08 | A API deve retornar respostas padronizadas (envelope: data, error, meta) | Alta |
| RF-020.09 | A API deve suportar webhooks para notificação assíncrona de eventos | Média |
| RF-020.10 | A API deve expor endpoints de health check e status | Alta |
| RF-020.11 | O sistema deve registar todas as chamadas à API para auditoria e métricas | Alta |
| RF-020.12 | A API deve suportar idioma via content negotiation (português, inglês) | Média |

## Critérios de Aceitação

- A documentação OpenAPI é gerada automaticamente e acessível via /docs
- Cada endpoint tem testes de integração automatizados
- Chamadas não autenticadas são rejeitadas com 401
- Chamadas sem permissão são rejeitadas com 403
- Rate limit é excedido com resposta 429 e header Retry-After
- A latência p95 da API é inferior a 500ms

## Regras de Negócio

- Clientes da API necessitam de registo e aprovação pelo administrador do inquilino
- Cada cliente tem um scope de permissões associado
- Tokens de acesso expiram após 60 minutos (configurável)
- Webhooks têm timeout de 5 segundos e retry com backoff exponencial (3 tentativas)

## Métricas

- Número de chamadas à API por cliente
- Latência média e por percentil (p50, p95, p99)
- Taxa de erros por endpoint
- Número de clientes registados
- Uptime da API (SLA)

## Documentos Relacionados

- [10 — Integrações](../../10-integracoes/index.md)
- [10 — Arquitectura API](../../10-integracoes/arquitetura-api.md)
- [03 — Arquitectura / API Gateway](../../03-arquitetura/api-gateway.md)
- [03 — Arquitectura / Autenticação](../../03-arquitetura/autenticacao.md)
