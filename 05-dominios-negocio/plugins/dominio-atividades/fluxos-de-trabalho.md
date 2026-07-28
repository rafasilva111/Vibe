# Atividades — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **licenca-atividade** | Licenciamento de actividade permanente |
| **comunicacao-previa** | Comunicação prévia de actividade eventual |
| **fiscalizacao-atividade** | Fiscalização de actividades |

```mermaid
flowchart TD
    A[Pedido] --> B[Análise Documental]
    B --> C{Vistoria Necessária?}
    C -->|Sim| D[Agendar Vistoria]
    C -->|Não| E[Análise Final]
    D --> F[Realizar Vistoria]
    F --> G{Parecer Favorável?}
    G -->|Sim| E
    G -->|Não| H[Indeferir]
    E --> I[Emitir Licença]
    H --> J[Notificar]
    I --> J
