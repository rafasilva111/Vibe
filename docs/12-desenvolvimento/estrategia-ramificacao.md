# Estratégia de Ramificação

## Propósito
Definir a estratégia de branches para versionamento.

## Modelo

```mermaid
flowchart LR
    main[main] --> dev[dev]
    dev --> feat[feature/*]
    dev --> fix[fix/*]
    main --> hotfix[hotfix/*]
    feat --> dev
    fix --> dev
    hotfix --> main
    dev --> release[release/*]
    release --> main
```

## Convenções

| Branch | Base | Destino | Descrição |
|---|---|---|---|
| `main` | — | — | Produção |
| `dev` | main | main | Integração |
| `feature/xxx` | dev | dev | Nova funcionalidade |
| `fix/xxx` | dev | dev | Correção |
| `hotfix/xxx` | main | main + dev | Correção urgente |
| `release/x.y` | dev | main | Preparação de release |
