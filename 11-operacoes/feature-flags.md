# Feature Flags

## Propósito
Definir o sistema de feature flags para activação gradual de funcionalidades.

## Provider

| Componente | Tecnologia |
|---|---|
| **Server-side** | LaunchDarkly / Unleash |
| **Client-side** | JavaScript SDK |

## Flags Típicas

| Flag | Descrição | Target |
|---|---|---|
| `novo-workflow` | Novo motor de workflows | 10% → 50% → 100% |
| `assistente-ai` | Assistente virtual | Inquilinos beta |
| `process-mining` | Módulo de process mining | Admin apenas |
| `modo-escuro` | Tema escuro | Utilizadores |

## Documentos Relacionados

- [Configuração](configuracao.md)
