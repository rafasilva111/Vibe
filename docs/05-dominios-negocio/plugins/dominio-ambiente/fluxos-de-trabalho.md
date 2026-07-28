# Ambiente — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **recolha-volumosos** | Recolha de resíduos volumosos |
| **denuncia-ambiental** | Tratamento de denúncia ambiental |

```mermaid
flowchart TD
    A[Pedido Recebido] --> B[Agendar Recolha]
    B --> C[Notificar Requerente]
    C --> D[Realizar Recolha]
    D --> E[Registo de Conclusão]
    E --> F[Feedback]
```
