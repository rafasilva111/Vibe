# Gestão de Processos — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **processo-generico** | Workflow genérico para processos administrativos |
| **processo-urgente** | Workflow com prazos reduzidos (urgência) |
| **processo-simplificado** | Workflow simplificado (instrução mínima) |
| **recurso** | Workflow de recurso hierárquico |

### Fluxo Genérico

```mermaid
flowchart TD
    A[Abertura] --> B[Triagem Automática]
    B --> C[Instrução]
    C --> D{Parecer Necessário?}
    D -->|Sim| E[Parecer]
    E --> C
    D -->|Não| F[Concluso para Decisão]
    F --> G[Despacho]
    G --> H{Favorável?}
    H -->|Sim| I[Emissão Documento]
    H -->|Não| J[Notificação Indeferimento]
    I --> K[Notificação]
    J --> K
    K --> L[Arquivo]
```

## Documentos Relacionados

- [04 — Workflow](../../../04-servicos-plataforma/plataforma-workflow.md)
- [03 — Diagramas de Estado](../../../03-arquitetura/diagramas-de-estado.md)
