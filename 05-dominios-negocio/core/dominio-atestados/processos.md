# Atestados — Processos

## Processos

| Processo | Descrição | Prazo |
|---|---|---|
| **Emissão de Atestado de Residência** | Comprovar morada na freguesia | 3 dias úteis |
| **Emissão de Atestado de Vida** | Comprovar que está vivo | Imediato |
| **Emissão de Atestado de Insuficiência Económica** | Comprovar baixos rendimentos | 5 dias úteis |
| **Emissão de Declaração** | Declaração genérica | 1 dia útil |
| **Segunda Via** | Reemissão de atestado | 1 dia útil |

### Emissão de Atestado de Residência

```mermaid
flowchart TD
    C[Cidadão Solicita] --> V{Residente na Freguesia?}
    V -->|Sim| CV[Verificar Comprovativo Morada]
    V -->|Não| R[Recusar - Orientar para junta correcta]
    CV --> OK{Documentos Válidos?}
    OK -->|Sim| E[Emitir Atestado]
    OK -->|Não| P[Pedir Documentos Correctos]
    P --> CV
    E --> A[Assinar Digitalmente]
    A --> ENT[Entregar ao Cidadão]
```

## Documentos Relacionados

- [Serviços](servicos.md)
- [Tarefas](tarefas.md)
