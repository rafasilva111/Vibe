# Cemitérios — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **inumacao** | Processo de inumação |
| **exumacao** | Processo de exumação |
| **concessao-jazigo** | Atribuição de concessão |

```mermaid
flowchart TD
    A[Pedido Recebido] --> B[Verificar Documentação]
    B --> C[Registar Óbito / Pedido]
    C --> D[Selecionar Local]
    D --> E[Calcular Taxa]
    E --> F[Emitir Guia de Pagamento]
    F --> G{Pagamento?}
    G -->|Sim| H[Realizar Serviço]
    G -->|Não| I[Cancelar Pedido]
    H --> J[Registar no Livro de Registo]
    J --> K[Atualizar Ocupação]
```
