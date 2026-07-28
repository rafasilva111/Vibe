# Plataforma — Notificações

## Propósito

Gerir o envio de notificações da Junta Observatory Platform para cidadãos e funcionários, através de múltiplos canais (email, SMS, push, caixa postal electrónica).

## Responsabilidades

- Enviar notificações transaccionais (estado de processos, prazos)
- Suportar múltiplos canais de envio
- Gerir templates de notificação
- Controlar preferências de notificação por utilizador

## Descrição Detalhada

### Canais de Notificação

| Canal | Latência | Custo | Limitações |
|---|---|---|---|
| **Email** | < 1 min | Baixo | Pode ir para spam |
| **SMS** | < 10 seg | Alto | 160 caracteres |
| **Push (App)** | < 5 seg | Baixo | Requer instalação da app |
| **Caixa Postal** | Imediato | Baixo | Apenas na plataforma |
| **WhatsApp (futuro)** | < 30 seg | Médio | API Meta Business |

### Tipos de Notificação

| Tipo | Canais | Prioridade |
|---|---|---|
| Confirmação de submissão | Email, Caixa Postal | Alta |
| Notificação de prazo | Email, SMS | Alta |
| Decisão de processo | Email, Caixa Postal | Alta |
| Documento emitido | Email, Caixa Postal | Média |
| Tarefa atribuída | Email, Push (app) | Alta |
| Alerta de sistema | Email (admin) | Crítica |

### Template Engine

As notificações são geradas a partir de templates configuráveis por inquilino, com suporte a variáveis dinâmicas e localização (pt-PT).

## Documentos Relacionados

- [02 — RF018](../02-requisitos/funcionais/rf018.md)
- [04 — Workflow](plataforma-workflow.md)
- [04 — Eventos](plataforma-eventos.md)
