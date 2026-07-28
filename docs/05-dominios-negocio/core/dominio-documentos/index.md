# Domínio — Documentos

## Propósito

Gerir o ciclo de vida completo dos documentos na Junta Observatory Platform, desde a captura até à eliminação, incluindo classificação, armazenamento, processamento (OCR), assinatura e arquivo.

## Entidades Principais

| Entidade | Descrição |
|---|---|
| **Documento** | Ficheiro com metadados associados |
| **VersaoDocumento** | Versão específica de um documento |
| **TipoDocumento** | Classificação do documento (CC, BI, comprovativo) |
| **PastaDocumental** | Agrupamento lógico de documentos |
| **Assinatura** | Registo de assinatura digital |
| **Processamento** | Resultado de OCR/extração |

## Regras de Negócio

- Documentos com dados pessoais são encriptados em repouso
- Versões anteriores são mantidas por 5 anos
- OCR é aplicado automaticamente a PDFs e imagens
- Documentos assinados digitalmente têm fé pública
- Política de retenção: 10 anos para documentos processuais
