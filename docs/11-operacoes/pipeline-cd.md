# Pipeline CD

## Propósito
Definir o pipeline de Continuous Deployment.

## Fluxo

```mermaid
flowchart LR
    A[Commit] --> B[CI Build + Test]
    B --> C[Docker Image]
    C --> D[Deploy Dev]
    D --> E[Testes Dev]
    E --> F[Deploy Staging]
    F --> G[Testes Staging]
    G --> H{Aprovado?}
    H -->|Sim| I[Deploy Produção]
    H -->|Não| J[Rollback]
```

## Gate

| Gate | Verificação |
|---|---|
| **CI** | Testes unitários, SAST, SCA |
| **Dev** | Testes de integração |
| **Staging** | Testes E2E, DAST, smoke tests |
| **Produção** | Aprovação manual + canary |
