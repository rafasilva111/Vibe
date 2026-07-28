# Revisões de Código

## Propósito
Definir o processo de code review.

## Regras

| Regra | Descrição |
|---|---|
| **Obrigatório** | Todo o código PR requer review |
| **Mínimo** | 1 approver (2 para core) |
| **Tempo** | Review em < 24h úteis |
| **Tamanho** | PR máximo 400 linhas |
| **Checklist** | Verificar: testes, segurança, estilo |

## Checklist

| Item | Descrição |
|---|---|
| **Testes** | Testes unitários incluídos e a passar |
| **Cobertura** | Cobertura não diminuiu |
| **Segurança** | Sem vulnerabilidades introduzidas |
| **Estilo** | Conforme normas de código |
| **Documentação** | APIs documentadas |
| **Performance** | Sem queries N+1, sem loops desnecessários |
