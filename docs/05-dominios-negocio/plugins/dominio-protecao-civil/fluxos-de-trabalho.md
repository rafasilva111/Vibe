# Proteção Civil — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **ocorrencia-emergencia** | Gestão de ocorrência de emergência |
| **exercicio-simulacao** | Planeamento e execução de exercício |

```mermaid
flowchart TD
    A[Ocorrência Recebida] --> B[Triagem e Classificação]
    B --> C{Grau de Emergência?}
    C -->|Alto| D[Acionar Equipa 1ª Intervenção]
    C -->|Médio| E[Agendar Intervenção]
    C -->|Baixo| F[Registo para Acompanhamento]
    D --> G[Coordenar Operações]
    G --> H{Ocorrência Controlada?}
    H -->|Sim| I[Desmobilizar Meios]
    H -->|Não| G
    I --> J[Relatório Pós-Ocorrência]
    E --> J
    F --> J
```
