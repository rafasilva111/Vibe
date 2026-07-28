# Trilha de Auditoria

## Propósito
Definir a trilha de auditoria para rastreabilidade de operações.

## Eventos Auditados

| Categoria | Eventos |
|---|---|
| **Autenticação** | Login, logout, falha de autenticação |
| **Processos** | Criação, alteração de estado, decisão |
| **Documentos** | Upload, download, eliminação |
| **Utilizadores** | Criação, alteração de permissões |
| **Configuração** | Alteração de parâmetros do sistema |
| **Dados Pessoais** | Acesso, exportação, eliminação |

## Armazenamento

- Logs de auditoria armazenados no Event Store (imutável)
- Retenção: 10 anos (conforme lei)
- Consulta disponível para DPO e auditores externos
- Exportação em formato PDF/CSV

## Documentos Relacionados

- [04 — Auditoria](../04-servicos-plataforma/plataforma-auditoria.md)
- [13 — RGPD](../13-governanca-conformidade/rgpd.md)
