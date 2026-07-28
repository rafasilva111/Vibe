# Protocolo e Comunicação — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **organizacao-evento** | Planeamento e execução de evento protocolar |
| **emissao-comunicado** | Redação e aprovação de comunicado |

```mermaid
flowchart TD
    A[Necessidade Identificada] --> B[Criar Dossier de Evento]
    B --> C[Checklist de Preparação]
    C --> D{Convidados?}
    D -->|Sim| E[Emitir Convites]
    D -->|Não| F[Continuar]
    E --> F
    F --> G[Coordenar Logística]
    G --> H[Realizar Evento]
    H --> I[Relatório Pós-Evento]
    I --> J[Arquivo]
```
