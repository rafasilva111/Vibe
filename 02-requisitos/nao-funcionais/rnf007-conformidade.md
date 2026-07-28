# RNF-007 — Conformidade

## Propósito

Garantir que a Junta Observatory Platform cumpre integralmente a legislação e regulamentação aplicável, incluindo RGPD, Código do Procedimento Administrativo, eIDAS e normas nacionais de administração pública digital.

## Descrição

A conformidade regulatória é um requisito crítico, dada a natureza dos dados processados e o contexto de administração pública. A plataforma deve ser compliant by design, incorporando os requisitos legais na arquitectura e nos processos.

## Requisitos

| ID | Requisito | Regulamento |
|---|---|---|
| RNF-007.01 | Recolha de dados pessoais apenas para finalidades determinadas e legítimas | RGPD Art. 5.º |
| RNF-007.02 | Consentimento explícito, livre e informado para tratamento de dados | RGPD Art. 7.º |
| RNF-007.03 | Direito de acesso do titular aos seus dados | RGPD Art. 15.º |
| RNF-007.04 | Direito de rectificação e apagamento ("direito ao esquecimento") | RGPD Art. 16.º, 17.º |
| RNF-007.05 | Portabilidade dos dados | RGPD Art. 20.º |
| RNF-007.06 | Notificação de violações de dados à CNPD em 72h | RGPD Art. 33.º |
| RNF-007.07 | Registo de actividades de tratamento (ROPA) | RGPD Art. 30.º |
| RNF-007.08 | Privacy by Design e Privacy by Default | RGPD Art. 25.º |
| RNF-007.09 | Prazo legal de decisão sobre requerimentos (60 dias) | CPA Art. 128.º |
| RNF-007.10 | Audiência prévia dos interessados antes da decisão final | CPA Art. 121.º |
| RNF-007.11 | Fundamentação das decisões de facto e de direito | CPA Art. 152.º |
| RNF-007.12 | Autenticação com níveis de segurança eIDAS (substancial, alto) | eIDAS Reg. 910/2014 |
| RNF-007.13 | Conformidade com o Regime Nacional de Identificação Digital | Decreto-Lei n.º 12/2021 |
| RNF-007.14 | Acessibilidade digital conforme WCAG 2.1 nível AA | DL n.º 83/2018 |

## Critérios de Aceitação

- Auditoria externa de RGPD não identifica não-conformidades críticas
- A CNPD aprova o registo de actividades de tratamento
- Certificação eIDAS para autenticação de cidadãos
- Testes de acessibilidade WCAG 2.1 AA passam sem erros críticos
- O CPA é cumprido em todos os fluxos de processo automatizados

## Estratégia

- Privacy Impact Assessment (PIA) realizado antes do lançamento
- Análise jurídica de cada fluxo de processo antes da implementação
- DPO indicado e integrado no ciclo de desenvolvimento
- Auditoria de conformidade trimestral automatizada
- Relatório de conformidade gerado automaticamente para a direcção

## Métricas

- Número de não-conformidades detectadas em auditoria
- Tempo médio de resolução de não-conformidades
- Percentagem de processos com avaliação de impacto realizada
- Taxa de consentimentos válidos registados
- Score de acessibilidade (Lighthouse, axe-core)

## Documentos Relacionados

- [13 — Governança e Conformidade](../../13-governanca-conformidade/index.md)
- [13 — RGPD](../../13-governanca-conformidade/rgpd.md)
- [13 — Lei Administrativa](../../13-governanca-conformidade/lei-administrativa.md)
- [01 — Regras de Negócio Globais](../../01-analise-de-negocio/regras-de-negocio-globais.md)
