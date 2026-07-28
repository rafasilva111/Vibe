# Estratégia de Testes

## Propósito
Definir a estratégia de testes da plataforma.

## Pirâmide

```mermaid
flowchart TD
    E2E[Testes E2E - 5%]
    INT[Testes Integração - 15%]
    UNIT[Testes Unitários - 80%]
```

## Cobertura

| Nível | Cobertura Mínima | Responsabilidade |
|---|---|---|
| **Unitários** | 80% | Desenvolvedor |
| **Integração** | 60% | Desenvolvedor |
| **E2E** | Principais fluxos | QA |

## Documentos Relacionados

- [Testes Unitários](testes-unidade.md)
- [Testes Integração](testes-integracao.md)
- [Testes E2E](testes-e2e.md)
