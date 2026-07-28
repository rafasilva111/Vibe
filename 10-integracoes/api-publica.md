# API Pública

## Propósito
Definir a API pública para integração com sistemas de parceiros.

## Endpoints

| Recurso | Métodos | Autenticação |
|---|---|---|
| `/servicos` | GET | API Key |
| `/casos` | GET, POST | OAuth 2.0 |
| `/documentos` | GET, POST | OAuth 2.0 |
| `/tarefas` | GET, PATCH | OAuth 2.0 |
| `/eventos` | GET | API Key |

## Limitações

| Limite | Valor |
|---|---|
| Requests por segundo | 100 |
| Tamanho máximo de payload | 10 MB |
| Timeout | 30s |
| Paginação | 100 items/página |

## Documentos Relacionados

- [04 — API](../04-servicos-plataforma/plataforma-api.md)
- [Autenticação Externa](autenticacao-externa.md)
