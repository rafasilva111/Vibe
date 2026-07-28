# Atendimento — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **atendimento-presencial** | Atendimento presencial com senha e fila |
| **atendimento-telefonico** | Atendimento por chamada telefónica |
| **atendimento-digital** | Resposta a pedido submetido online |
| **gestao-reclamacao** | Registo e tratamento de reclamações |

### Fluxo de Atendimento Presencial

```mermaid
flowchart TD
    A[Check-in Senha] --> B{Senha Prioritária?}
    B -->|Sim| C[Fila Prioritária]
    B -->|Não| D[Fila Normal]
    C --> E[Balcão Atendimento]
    D --> E
    E --> F[Registo da Interacção]
    F --> G{Abrir Processo?}
    G -->|Sim| H[Criar Caso]
    G -->|Não| I[Concluir]
    H --> I
```

## Documentos Relacionados

- [Processos](processos.md)
- [04 — Workflow](../../../04-servicos-plataforma/plataforma-workflow.md)
