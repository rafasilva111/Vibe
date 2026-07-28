# 14 — Qualidade

## Propósito

Definir a estratégia de qualidade da Junta Observatory Platform, incluindo as práticas de garantia de qualidade, critérios de aceitação, métricas de qualidade e processos de revisão.

## Responsabilidades

- Estabelecer os standards de qualidade para todo o projecto
- Definir os processos de QA, revisão de código e teste
- Garantir que cada entregável cumpre os critérios de aceitação
- Monitorizar e reportar métricas de qualidade

## Documentos

| Documento | Descrição |
|---|---|
| [Estratégia de Qualidade](estrategia-qualidade.md) | Abordagem global de qualidade |
| [Critérios de Aceitação Globais](criterios-aceitacao-globais.md) | Critérios transversais a todos os requisitos |
| [Métricas de Qualidade](metricas-qualidade.md) | Métricas para avaliar a qualidade |
| [Revisões de Código](revisoes-codigo.md) | Processo de code review |
| [Análise Estática](analise-estatica.md) | Ferramentas e regras de análise estática |
| [Testes de Regressão](testes-regressao.md) | Estratégia de testes de regressão |
| [Processo de QA](processo-qa.md) | Fluxo de garantia de qualidade |

## Pirâmide de Testes

```mermaid
flowchart TD
    subgraph "Pirâmide de Testes"
        E2E["Testes E2E (5%)"]
        INT["Testes de Integração (15%)"]
        UNIT["Testes Unitários (60%)"]
        STATIC["Análise Estática (10%)"]
        MANUAL["Testes Manuais Exploratórios (10%)"]
    end
    STATIC --> UNIT
    UNIT --> INT
    INT --> E2E
    E2E --> MANUAL
```

## Critérios de Qualidade

| Dimensão | Critério | Métrica |
|---|---|---|
| **Funcional** | Todos os RF implementados conforme especificação | Cobertura de acceptance tests |
| **Desempenho** | RNF-001 cumprido | Testes de carga automatizados |
| **Segurança** | Sem vulnerabilidades críticas | SAST + DAST + pentest |
| **Código** | Código limpo e bem estruturado | Code review + análise estática |
| **Cobertura** | ≥ 80% unit, ≥ 60% integration | SonarQube / JaCoCo |
| **Documentação** | Documentação actualizada | Revisão trimestral |

## Documentos Relacionados

- [02 — Requisitos](../02-requisitos/index.md)
- [12 — Desenvolvimento / Estratégia de Testes](../12-desenvolvimento/estrategia-testes.md)
- [12 — Desenvolvimento / Testes Unidade](../12-desenvolvimento/testes-unidade.md)
- [12 — Desenvolvimento / Testes Integração](../12-desenvolvimento/testes-integracao.md)
- [12 — Desenvolvimento / Testes E2E](../12-desenvolvimento/testes-e2e.md)
- [12 — Desenvolvimento / Testes Carga](../12-desenvolvimento/testes-carga.md)
- [12 — Desenvolvimento / Testes Segurança](../12-desenvolvimento/testes-seguranca.md)
