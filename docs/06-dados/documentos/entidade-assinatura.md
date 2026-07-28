# Assinatura

## Descrição
Registo de assinatura digital de um documento.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| documento_id | UUID (FK) | Documento assinado |
| signatario_id | UUID (FK) | Utilizador que assinou |
| metodo | Enum | CMD, Cartão Cidadão, eIDAS |
| certificado | Text | Dados do certificado |
| hash_assinatura | String | Hash da assinatura |
| assinado_em | Datetime | Data da assinatura |
