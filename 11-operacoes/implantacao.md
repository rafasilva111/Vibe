# Implantação (Deploy)

## Propósito
Definir a estratégia de deploy da Junta Observatory Platform.

## Estratégia

| Ambiente | Estratégia | Descrição |
|---|---|---|
| **Produção** | Rolling update | Zero downtime, gradual |
| **Staging** | Rolling update | Rápido, para testes |
| **Desenvolvimento** | Recreate | Simples, rápido |

## Rolling Update

| Parâmetro | Valor |
|---|---|
| **Max unavailable** | 25% |
| **Max surge** | 25% |
| **Min ready seconds** | 30s |
| **Progress deadline** | 300s |

## Documentos Relacionados

- [Pipeline CD](pipeline-cd.md)
