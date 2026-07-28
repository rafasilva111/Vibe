# Licenciamento — Processos

## Processos

| Processo | Descrição | Prazo |
|---|---|---|
| **Licença de Obra Menor** | Obras de conservação, reparação | 20 dias úteis |
| **Licença de Obra Maior** | Obras de construção, ampliação | 60 dias úteis (CM) |
| **Ocupação de Via Pública** | Esplanadas, andaimes, contentores | 15 dias úteis |
| **Actividades Eventuais** | Feiras, eventos, espectáculos | 30 dias úteis |
| **Publicidade** | Afixação de publicidade | 20 dias úteis |
| **Renovação** | Renovação de licença existente | 10 dias úteis |

### Licença de Obra Menor

```mermaid
flowchart TD
    A[Pedido Submetido] --> B[Verificar Documentação]
    B --> C{Documentos Completos?}
    C -->|Sim| D[Análise Técnica]
    C -->|Não| E[Pedir Correções]
    E --> B
    D --> F{Conforme?}
    F -->|Sim| G[Emissão Licença]
    F -->|Não| H[Notificar Indeferimento]
    G --> I[Notificar + Cobrar Taxa]
    H --> I
    I --> J[Arquivo]
```

## Documentos Relacionados

- [Serviços](servicos.md)
- [Fluxos de Trabalho](fluxos-de-trabalho.md)
