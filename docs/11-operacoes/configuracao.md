# Configuração

## Propósito
Definir a gestão de configuração dos serviços.

## Fontes

| Fonte | Conteúdo | Exemplo |
|---|---|---|
| **ConfigMaps** | Configuração não sensível | URL de serviços, portas |
| **Secrets** | Configuração sensível | Passwords, API keys |
| **Environment** | Override específico | Ambiente (dev/staging/prod) |

## Hierarquia

1. Valores padrão (código)
2. ConfigMap (K8s)
3. Secrets (Vault)
4. Environment variables
5. Feature Flags (runtime)

## Documentos Relacionados

- [Feature Flags](feature-flags.md)
