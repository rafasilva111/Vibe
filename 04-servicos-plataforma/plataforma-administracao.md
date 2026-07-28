# Plataforma — Administração

## Propósito

Disponibilizar funcionalidades de administração do sistema para gestores de inquilino e administradores globais da Junta Observatory Platform.

## Responsabilidades

- Gerir inquilinos (criação, suspensão, cancelamento)
- Gerir configurações globais e por inquilino
- Monitorizar a saúde do sistema
- Gerir planos de subscrição e limites

## Descrição Detalhada

### Funcionalidades

| Módulo | Funcionalidade | Perfil |
|---|---|---|
| **Inquilinos** | Criar, editar, suspender, cancelar | Admin Global |
| **Planos** | Atribuir plano, alterar limites | Admin Global |
| **Configurações** | Parâmetros globais, personalização | Admin Global, Admin Inquilino |
| **Monitorização** | Dashboard de saúde, alertas | Admin Global, Admin Inquilino |
| **Logs de Auditoria** | Consulta e exportação | Admin Global, DPO |
| **Manutenção** | Anúncios, janelas de manutenção | Admin Global |

### Perfis de Administração

| Perfil | Âmbito | Responsabilidades |
|---|---|---|
| **Admin Global** | Toda a plataforma | Gerir inquilinos, planos, suporte |
| **Admin de Inquilino** | Junta específica | Gerir utilizadores, configurações locais |
| **DPO** | Toda a plataforma | Auditoria, RGPD, privacidade |
| **Suporte** | Tickets de suporte | Responder a pedidos das juntas |

## Documentos Relacionados

- [03 — Multi-Inquilino](../03-arquitetura/multi-inquilino.md)
- [05 — Utilizadores](plataforma-utilizadores.md)
- [13 — Governança](../13-governanca-conformidade/index.md)
