# Documentos — Eventos

## Eventos de Domínio

| Evento | Significado | Consumidores |
|---|---|---|
| `documento.uploaded` | Documento carregado | Processamento, Índice |
| `documento.processado` | OCR e classificação concluídos | Casos, Pesquisa |
| `documento.assinado` | Assinatura digital concluída | Casos, Notificações |
| `documento.partilhado` | Documento partilhado com terceiro | Auditoria |
| `documento.eliminado` | Documento eliminado (soft delete) | Auditoria, RGPD |

## Documentos Relacionados

- [04 — Eventos](../../../04-servicos-plataforma/plataforma-eventos.md)
