# Integrações — Arquitetura API

## Propósito
Definir a arquitetura da API de integração da Junta Observatory Platform.

## Princípios

| Princípio | Descrição |
|---|---|
| **RESTful** | APIs REST com recursos bem definidos |
| **Versionamento** | URI path (`/api/v1/`) |
| **Autenticação** | OAuth 2.0 / API Keys |
| **Documentação** | OpenAPI 3.0 |
| **Rate Limiting** | 100 req/s por tenant |
