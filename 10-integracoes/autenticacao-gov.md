# Autenticação.gov

## Propósito
Integração com o sistema Autenticação.gov para autenticação de funcionários públicos.

## Protocolo

| Aspecto | Detalhe |
|---|---|
| **Protocolo** | SAML 2.0 / OIDC |
| **Perfil** | Funcionário público |
| **Dados** | Nome, email, NIF, cargo, entidade |
| **Nível** | Nível 4 (cartão de cidadão) |

## Fluxo

1. Utilizador seleciona "Autenticação.gov"
2. Redirecionado para o IdP nacional
3. Autentica com cartão de cidadão / CMD
4. Recebe token SAML/OIDC com atributos profissionais
5. Mapeamento para perfil de funcionário na plataforma

## Documentos Relacionados

- [Sistemas Nacionais](sistemas-nacionais.md)
- [03 — Autenticação](../03-arquitetura/autenticacao.md)
