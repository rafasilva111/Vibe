# Feiras e Mercados — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **atribuicao-lugar** | Atribuição de lugar de feira/mercado |
| **licenca-feirante** | Emissão de licença de feirante |

```mermaid
flowchart TD
    A[Pedido Recebido] --> B[Verificar Disponibilidade]
    B --> C{Existe Lugar?}
    C -->|Sim| D[Atribuir Lugar]
    C -->|Não| E[Lista de Espera]
    D --> F[Calcular Taxa]
    F --> G[Emitir Licença]
    G --> H[Cobrar Taxa]
    H --> I[Ativo]
```
