# Plataforma — Automação

## Propósito

Descrever o motor de automação de regras e acções da Junta Observatory Platform, permitindo definir triggers, condições e acções automáticas sem intervenção manual.

## Responsabilidades

- Executar regras de negócio automáticas (triagem, prazos, notificações)
- Permitir configuração de regras por administradores
- Auditar todas as execuções automáticas

## Descrição Detalhada

### Tipos de Automação

| Tipo | Exemplo | Gatilho |
|---|---|---|
| **Triagem** | Classificar pedido automaticamente por tipo | Criação de caso |
| **Prazo** | Notificar cidadão 5 dias antes do prazo | Scheduler diário |
| **Notificação** | Enviar SMS quando documento é emitido | Transição de estado |
| **Validação** | Validar documento automaticamente (OCR) | Upload de documento |
| **Atribuição** | Atribuir tarefa ao técnico com menos carga | Transição para instrução |
| **Arquivo** | Arquivar processo 30 dias após conclusão | Scheduler diário |

### Fluxo de Automação

```mermaid
flowchart TD
    E[Evento] --> R[Motor de Regras]
    R --> C{Condições Satisfeitas?}
    C -->|Sim| A[Executar Acção]
    C -->|Não| F[Ignorar]
    A --> L[Registo de Auditoria]
    A --> N[Notificar (se aplicável)]
```

## Documentos Relacionados

- [04 — Workflow](plataforma-workflow.md)
- [02 — RF004](../02-requisitos/funcionais/rf004.md)
- [01 — Regras de Negócio Globais](../01-analise-de-negocio/regras-de-negocio-globais.md)
