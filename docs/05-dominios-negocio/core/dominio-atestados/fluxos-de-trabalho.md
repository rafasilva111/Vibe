# Atestados — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **atestado-residencia** | Emissão de atestado de residência |
| **atestado-vida** | Emissão de atestado de vida |
| **atestado-insuficiencia-economica** | Emissão de atestado de insuficiência económica |
| **declaracao-generica** | Emissão de declaração |

### Fluxo de Emissão

```mermaid
flowchart TD
    A[Pedido Recebido] --> B[Validar Dados do Cidadão]
    B --> C[Verificar Documentos]
    C --> D{Documentos OK?}
    D -->|Sim| E[Gerar Atestado]
    D -->|Não| F[Notificar Cidadão]
    F --> C
    E --> G[Assinar Digitalmente]
    G --> H[Registar Emissão]
    H --> I[Entregar/Disponibilizar]
```

## Documentos Relacionados

- [04 — Workflow](../../../04-servicos-plataforma/plataforma-workflow.md)
