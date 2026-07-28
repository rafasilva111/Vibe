# Direito ao Apagamento

## Propósito
Definir o processo para exercício do direito ao apagamento (RGPD Art. 17).

## Fluxo

```mermaid
flowchart TD
    A[Cidadão Solicita] --> B[Verificar Identidade]
    B --> C[Identidade Confirmada?]
    C -->|Sim| D[Identificar Dados]
    C -->|Não| E[Pedir Mais Info]
    E --> B
    D --> F[Verificar Obrigações Legais]
    F --> G{Há Obrigação Legal?}
    G -->|Sim| H[Anonimizar + Bloquear]
    G -->|Não| I[Eliminar Dados]
    H --> J[Notificar Cidadão]
    I --> J
    J --> K[Registo de Auditoria]
```

## Prazos

| Etapa | Prazo |
|---|---|
| Confirmação de receção | 5 dias úteis |
| Resposta ao titular | 30 dias (prorrogável +30) |
| Execução do apagamento | 30 dias após decisão |
| Notificação a terceiros | 15 dias após execução |
