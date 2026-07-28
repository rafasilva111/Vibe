# Domínio — Atestados

## Propósito

Gerir a emissão de certidões e atestados pela junta de freguesia, incluindo atestados de residência, de vida, de insuficiência económica e outros documentos comprovativos.

## Entidades Principais

| Entidade | Descrição |
|---|---|
| **PedidoAtestado** | Pedido de emissão de atestado |
| **Atestado** | Documento emitido |
| **Declaracao** | Declaração associada ao atestado |
| **Taxa** | Taxa aplicável ao atestado |
| **ModeloAtestado** | Template/configuração do atestado |

## Regras de Negócio

- Atestado de residência: requer comprovativo de morada actual (≤ 3 meses)
- Atestado de vida: presencial obrigatório (ou CMD com vídeo-chamada)
- Atestado de insuficiência económica: requer comprovativos de rendimentos
- Validade do atestado: 30 dias (excepto se especificado em contrário)
- Taxa: isenção para atestados de insuficiência económica
