# Autenticação Externa

## Propósito
Definir a autenticação para sistemas externos que acedem à API.

## Métodos

| Método | Público | Utilização |
|---|---|---|
| **OAuth 2.0** | Parceiros | Fluxo client credentials |
| **API Key** | Integrações simples | Header `X-API-Key` |
| **JWT** | Serviços internos | mTLS + JWT |

## Gestão de Chaves

- API Keys geridas no painel de administração
- ROTAÇÃO obrigatória a cada 180 dias
- Registo de todas as chamadas com log de auditoria
- Revogação imediata em caso de incidente

## Documentos Relacionados

- [03 — Autenticação](../03-arquitetura/autenticacao.md)
