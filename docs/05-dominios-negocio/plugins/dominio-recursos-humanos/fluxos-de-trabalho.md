# Recursos Humanos — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **recrutamento** | Processo de recrutamento e seleção |
| **ferias** | Marcação e aprovação de férias |
| **avaliacao-desempenho** | Processo SIADAP |

```mermaid
flowchart TD
    A[Pedido de Férias] --> B{Saldo Disponível?}
    B -->|Sim| C[Submeter a Aprovação]
    B -->|Não| D[Ajustar Datas]
    C --> E{Aprovação Chefe?}
    E -->|Sim| F[Registar Férias]
    E -->|Não| G[Reformular Pedido]
    F --> H[Atualizar Saldo]
    G --> A
```
