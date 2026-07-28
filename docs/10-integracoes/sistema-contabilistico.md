# Sistema Contabilístico

## Propósito
Integração com o sistema contabilístico da junta.

## Dados

| Dado | Direção | Frequência |
|---|---|---|
| **Receitas** | Plataforma → Contabilidade | Diária |
| **Despesas** | Contabilidade → Plataforma | Mensal |
| **Orçamento** | Contabilidade → Plataforma | Anual |
| **Compromissos** | Plataforma → Contabilidade | Tempo real |

## Formato

- SAF-T (PT) para exportação
- API REST para integração em tempo real
- Ficheiro CSV/XLSX como fallback

## Documentos Relacionados

- [05 — Financeiro](../05-dominios-negocio/plugins/dominio-financeiro/index.md)
