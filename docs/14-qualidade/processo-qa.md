# Processo de QA

## Propósito
Definir o processo de Quality Assurance.

## Fluxo

```mermaid
flowchart LR
    A[Desenvolvimento] --> B[Code Review]
    B --> C[Testes Automatizados]
    C --> D[QA Review]
    D --> E{Aprovado?}
    E -->|Sim| F[Deploy Staging]
    E -->|Não| G[Correções]
    G --> B
    F --> H[Testes Staging]
    H --> I{OK?}
    I -->|Sim| J[Deploy Produção]
    I -->|Não| G
```

## Responsabilidades

| Perfil | Responsabilidade |
|---|---|
| **Desenvolvedor** | Testes unitários, code style |
| **Tech Lead** | Code review, testes integração |
| **QA** | Testes E2E, testes manuais, smoke tests |
| **Product Owner** | Aceitação, testes de usabilidade |
