# Espaços — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **reserva-espaco** | Reserva de espaço municipal |

```mermaid
flowchart TD
    A[Pedido Recebido] --> B[Verificar Disponibilidade]
    B --> C{Disponível?}
    C -->|Sim| D[Calcular Tarifa]
    C -->|Não| E[Sugerir Alternativas]
    D --> F[Aguardar Pagamento Caução]
    F --> G{Pagamento?}
    G -->|Sim| H[Confirmar Reserva]
    G -->|Não| I[Cancelar Pedido]
    H --> J[Ocupação]
    J --> K[Vistoria Pós-Ocupação]
    K --> L{Danos?}
    L -->|Não| M[Devolver Caução]
    L -->|Sim| N[Reter Caução]
```

## Documentos Relacionados

- [04 — Workflow](../../../04-servicos-plataforma/plataforma-workflow.md)
