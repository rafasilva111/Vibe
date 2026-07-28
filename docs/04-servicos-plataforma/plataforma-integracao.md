# Plataforma — Integração

## Propósito

Disponibilizar a camada de integração da Junta Observatory Platform, permitindo a ligação com sistemas externos (financeiros, RH, SIG, plataformas nacionais).

## Responsabilidades

- Expor APIs e webhooks para integração
- Gerir conectores para sistemas externos
- Orquestrar sincronização bidireccional de dados
- Monitorizar o estado das integrações

## Descrição Detalhada

### Tipos de Integração

| Tipo | Exemplos | Padrão |
|---|---|---|
| **API REST** | SIG, SIOE, RNA | OAuth 2.0 + OpenAPI |
| **Webhook** | Notificações para sistemas externos | POST com payload JSON |
| **Ficheiro** | Importação/exportação CSV, XML, XLSX | S3 + scheduler |
| **Base de Dados** | Réplica de leitura (RH, Financeiro) | View ou CDC |
| **LDAP** | Sincronização de utilizadores | LDAP bind + query |
| **Assinatura** | CMD, CC, eIDAS | OIDC + bibliotecas nacionais |

### Conectores Nacionais

| Sistema | Protocolo | Dados | Direcção |
|---|---|---|---|
| **Autenticação.gov** | SAML/OIDC | Identidade | Import |
| **Chave Móvel Digital** | OIDC | Identidade + Assinatura | Bidireccional |
| **eIDAS** | SAML/OIDC | Identidade UE | Import |
| **SIOE** | REST | Organigrama | Import |
| **RNA** | API | Associações | Import |
| **ePortugal** | API | Serviços partilhados | Bidireccional |

## Documentos Relacionados

- [10 — Integrações](../10-integracoes/index.md)
- [04 — API](plataforma-api.md)
- [03 — Autenticação](../03-arquitetura/autenticacao.md)
