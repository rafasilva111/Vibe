# Plataforma Junta Observatory

> O Sistema Operativo de uma Junta de Freguesia.

## Descrição de Alto Nível

A **Junta Observatory Platform** é uma plataforma SaaS concebida para modelar, executar, observar, medir e melhorar continuamente todos os processos internos de uma Junta de Freguesia portuguesa. Actua como camada única de orquestração digital, unificando atendimento, licenciamento, gestão documental, workflows, relatórios, inteligência artificial e observabilidade num ecossistema coerente e extensível.

A plataforma adopta uma arquitectura de **microserviços** com **event sourcing híbrido**, organizada em **Bounded Contexts** segundo princípios de **Domain-Driven Design** e **Arquitectura Hexagonal**. O modelo de domínio reflecte a estrutura organizativa, legal e operacional das Juntas de Freguesia em Portugal, incluindo conformidade com RGPD, eIDAS, Chave Móvel Digital, Autenticação.gov e Lei Administrativa.

## Propósito da Documentação

Esta documentação constitui a **Especificação de Requisitos de Software (SRS)** alinhada com a norma **IEEE 29148**, estendida para cobrir arquitectura empresarial, modelação de processos de negócio (BPM), observabilidade, process mining, analítica e inteligência artificial.

Serve como:

- Fonte única de verdade para a equipa de desenvolvimento
- Referência para integradores externos e parceiros tecnológicos
- Guia de negócio para dirigentes e funcionários das Juntas de Freguesia
- Base para concursos públicos e processos de procurement
- Artefacto de conformidade regulatória e auditoria

## Organização da Documentação

A documentação está organizada em **16 secções temáticas**, numeradas para navegação sequencial:

| Secção | Conteúdo |
|---|---|
| [00 — Visão Estratégica](00-visao-estrategica/index.md) | Contexto, objectivos, âmbito, stakeholders, glossário, roadmap, modelo de valor |
| [01 — Análise de Negócio](01-analise-de-negocio/index.md) | Organização, governo, actores, permissões, regras de negócio, ciclo de vida |
| [02 — Requisitos](02-requisitos/index.md) | Requisitos funcionais (RF) e não funcionais (RNF) |
| [03 — Arquitectura](03-arquitetura/index.md) | Diagramas C4, DDD, microserviços, segurança, infraestrutura |
| [04 — Serviços Plataforma](04-servicos-plataforma/index.md) | Catálogo detalhado dos serviços internos da plataforma |
| [05 — Domínios de Negócio](05-dominios-negocio/index.md) | Domínios core e plugin modelados por Bounded Contexts |
| [06 — Dados](06-dados/index.md) | Modelo de dados, entidades, relacionamentos, diagrama ER |
| [07 — Interface Utilizador](07-interface-utilizador/index.md) | Design system, navegação, componentes, acessibilidade |
| [08 — Observabilidade](08-observabilidade/index.md) | Eventos, métricas, logs, tracing, process mining, alertas |
| [09 — Inteligência Artificial](09-inteligencia-artificial/index.md) | Assistente, recomendações, previsões, pesquisa semântica |
| [10 — Integrações](10-integracoes/index.md) | API, conectores, identidade digital, sistemas nacionais |
| [11 — Operações](11-operacoes/index.md) | Infraestrutura, deployment, backup, disaster recovery |
| [12 — Desenvolvimento](12-desenvolvimento/index.md) | Standards, CI/CD, testes, versionamento semântico |
| [13 — Governança e Conformidade](13-governanca-conformidade/index.md) | RGPD, segurança, lei administrativa, acessibilidade |
| [14 — Qualidade](14-qualidade/index.md) | Estratégia de qualidade, critérios de aceitação, QA |
| [15 — Projecto](15-projeto/index.md) | Fases, entregáveis, marcos, riscos, cronograma |

## Como Navegar

- **Leitores de negócio**: comece pela [Visão Estratégica](00-visao-estrategica/index.md) e [Análise de Negócio](01-analise-de-negocio/index.md)
- **Equipa técnica**: comece pela [Arquitectura](03-arquitetura/index.md) e [Requisitos](02-requisitos/index.md)
- **Integradores**: consulte [Integrações](10-integracoes/index.md) e [API Pública](10-integracoes/api-publica.md)
- **Operações**: consulte [Operações](11-operacoes/index.md) e [Observabilidade](08-observabilidade/index.md)
- **Qualidade**: consulte [Qualidade](14-qualidade/index.md)
- **Conformidade**: consulte [Governança e Conformidade](13-governanca-conformidade/index.md)

## Convenções de Nomenclatura

- **Ficheiros**: minúsculas com hífenes (`servico-workflow.md`)
- **Pastas**: minúsculas com hífenes (`dominio-licenciamento/`)
- **Identificadores RF**: prefixo `rf` + número (`rf001-catalogo-de-servicos.md`)
- **Identificadores RNF**: prefixo `rnf` + número (`rnf001-desempenho.md`)
- **Entidades**: prefixo `entidade-` + nome (`entidade-workflow.md`)
- **Serviços plataforma**: prefixo `plataforma-` + nome (`plataforma-workflow.md`)
- **Domínios**: prefixo `dominio-` + nome (`dominio-licenciamento/`)
- **Ligações**: relativas, sem extensão, estilo `[texto](caminho/para/ficheiro)`

## Standards de Documentação

Cada ficheiro `*.md` segue o template:

```markdown
# Título

## Propósito

## Responsabilidades

## Descrição Detalhada

## Requisitos

## Regras de Negócio

## Critérios de Aceitação

## Melhorias Futuras

## Documentos Relacionados
```

Quando aplicável, incluir diagramas **Mermaid** para representar fluxos, estados, relações e arquitecturas.

## Documentos Relacionados

- [IEEE 29148-2018 — Systems and Software Engineering — Requirements Engineering](https://standards.ieee.org/standard/29148-2018.html)
- [Domain-Driven Design — Eric Evans (2003)](https://www.domainlanguage.com/)
- [C4 Model for Visualising Software Architecture — Simon Brown](https://c4model.com/)
- [RGPD — Regulamento (UE) 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- [Lei n.º 75/2013 — Regime Jurídico das Autarquias Locais](https://diariodarepublica.pt/dr/legislacao-consolidada/lei/2013-34546475)
