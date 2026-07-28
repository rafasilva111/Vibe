# Documentos — Fluxos de Trabalho

## Fluxos

| Workflow | Descrição |
|---|---|
| **upload-documento** | Submissão, validação e processamento |
| **assinatura-digital** | Assinatura com CMD/CC/eIDAS |
| **partilha-externa** | Partilha com entidades externas |
| **eliminacao-programada** | Eliminação conforme política de retenção |

### Fluxo de Assinatura Digital

```mermaid
flowchart TD
    A[Documento Pronto] --> B[Seleccionar Método]
    B --> C[CMD]
    B --> D[Cartão Cidadão]
    B --> E[eIDAS]
    C --> F[Redireccionar CMD]
    D --> G[Ler CC + PIN]
    E --> H[Redireccionar eIDAS]
    F --> I[Assinatura Realizada]
    G --> I
    H --> I
    I --> J[Validar Assinatura]
    J --> K[Armazenar Documento Assinado]
    K --> L[Notificar Interessados]
```

## Documentos Relacionados

- [04 — Workflow](../../../04-servicos-plataforma/plataforma-workflow.md)
