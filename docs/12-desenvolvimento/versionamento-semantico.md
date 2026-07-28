# Versionamento Semântico

## Propósito
Definir a política de versionamento semântico.

## Formato

`MAJOR.MINOR.PATCH` (ex: 1.3.2)

| Componente | Incremento | Exemplo |
|---|---|---|
| **MAJOR** | Mudanças incompatíveis | 1.0.0 → 2.0.0 |
| **MINOR** | Novas funcionalidades retrocompatíveis | 1.0.0 → 1.1.0 |
| **PATCH** | Correções retrocompatíveis | 1.0.0 → 1.0.1 |

## Tags

- Tags git: `v1.0.0`
- Imagens Docker: `v1.0.0`, `latest`
- API: versão no path `/api/v1/`
