# Testes de Segurança

## Propósito
Definir a estratégia de testes de segurança.

## Tipos

| Tipo | Frequência | Ferramenta |
|---|---|---|
| **SAST** | Cada commit | SonarQube |
| **SCA** | Cada commit | Trivy, Snyk |
| **DAST** | Semanal | OWASP ZAP |
| **Pentest** | Anual | Equipa externa |
| **Image Scan** | Cada build | Trivy |

## Verificações

| Verificação | Descrição |
|---|---|
| **Injeção SQL** | Parameterised queries obrigatório |
| **XSS** | Output encoding |
| **CSRF** | Tokens anti-CSRF |
| **Autenticação** | Testes de bypass |
| **Autorização** | Testes de escalamento de privilégios |
