# Financeiro — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **processamento-despesa** | Processamento de despesa desde requisição ao pagamento |
| **cobranca-taxa** | Cobrança de taxa desde liquidação ao recebimento |
| **execucao-orcamental** | Controlo de execução orçamental |

```mermaid
flowchart TD
    A[Requisição] --> B{Cabimento Orçamental?}
    B -->|Sim| C[Registar Compromisso]
    B -->|Não| D[Recusar]
    C --> E[Autorização Superior]
    E --> F{Fatura Recebida?}
    F -->|Sim| G[Validar Fatura]
    F -->|Não| H[Aguardar Fatura]
    G --> I[Processar Pagamento]
    I --> J[Ordenar Pagamento]
    J --> K[Registar Despesa]
    H --> F
```
