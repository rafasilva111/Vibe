# Atendimento — Processos

## Processos

| Processo | Descrição | Gatilho |
|---|---|---|
| **Atendimento Presencial** | Atendimento na loja de cidadão / junta | Cidadão presencial |
| **Atendimento Telefónico** | Atendimento por chamada telefónica | Chamada recebida |
| **Atendimento Digital** | Pedido submetido via portal | Formulário online |
| **Agendamento** | Marcação de atendimento presencial | Cidadão agenda |
| **Reclamação** | Registo e tratamento de reclamação | Cidadão reclama |
| **Sugestão** | Registo de sugestão | Cidadão sugere |

### Atendimento Presencial

```mermaid
flowchart TD
    C[Cidadão Chega] --> S[Senha / Check-in]
    S --> F[Fila de Espera]
    F --> T[Técnico Atende]
    T --> R{Resolvido?}
    R -->|Sim| E[Encaminhar / Concluir]
    R -->|Não| A[Abrir Processo]
    A --> E
    E --> FB[Feedback]
```

## Documentos Relacionados

- [Serviços](servicos.md)
- [Tarefas](tarefas.md)
- [Fluxos de Trabalho](fluxos-de-trabalho.md)
