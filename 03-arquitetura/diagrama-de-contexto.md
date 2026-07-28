# Diagrama de Contexto (C4 Nível 1)

## Propósito

Fornecer uma visão de alto nível do sistema Junta Observatory Platform, mostrando o sistema no seu contexto operacional, os seus utilizadores e os sistemas externos com que interage.

## Responsabilidades

- Mostrar o sistema como uma caixa preta no centro do ecossistema
- Identificar todos os actores humanos e sistemas externos
- Estabelecer as relações de alto nível entre o sistema e o exterior

## Descrição Detalhada

```mermaid
architecture-beta
    group api(cloud)[Ecossistema Junta Observatory]

    service jop(server)[Junta Observatory<br/>Platform] in api

    group cidadao[Utilizadores]
    service cid(server)[Cidadão] in cidadao
    service func(server)[Funcionário] in cidadao
    service dirig(server)[Dirigente] in cidadao
    service admin(server)[Administrador] in cidadao

    group gov[Identidade Digital]
    service cmd(server)[Chave Móvel Digital] in gov
    service agov(server)[Autenticação.gov] in gov
    service eidas(server)[eIDAS Wallet] in gov

    group nac[Plataformas Nacionais]
    service eport(server)[ePortugal] in nac
    service rnid(server)[RNID / RNPC] in nac
    service sig(server)[SIG Nacional] in nac

    group fin[Financeiro]
    service erp(server)[Sistema Contabilístico] in fin
    service pay(server)[Gateway Pagamentos] in fin

    group com[Comunicação]
    service sms(server)[SMS Gateway] in com
    service mail(server)[Email Gateway] in com

    cid --> jop
    func --> jop
    dirig --> jop
    admin --> jop

    jop --> cmd
    jop --> agov
    jop --> eidas
    jop --> eport
    jop --> rnid
    jop --> sig
    jop --> erp
    jop --> pay
    jop --> sms
    jop --> mail

    group audit[Auditoria / Conformidade]
    service cnpd(server)[CNPD] in audit
    service dpo(server)[DPO Interno] in audit
    cnpd --> jop
    dpo --> jop
```

### Descrição dos Elementos

| Elemento | Tipo | Descrição |
|---|---|---|
| **Junta Observatory Platform** | Sistema | Plataforma SaaS que modela, executa, observa e melhora processos de Juntas de Freguesia |
| **Cidadão** | Actor humano | Munícipe que solicita serviços e consulta processos |
| **Funcionário** | Actor humano | Colaborador da Junta que opera a plataforma |
| **Dirigente** | Actor humano | Presidente, Vogais que decidem processos |
| **Administrador** | Actor humano | Configurador da plataforma por inquilino |
| **Chave Móvel Digital** | Sistema externo | Autenticação digital de cidadãos |
| **Autenticação.gov** | Sistema externo | Autenticação da Administração Pública |
| **eIDAS Wallet** | Sistema externo | Carteira digital europeia |
| **ePortugal** | Sistema externo | Portal de serviços públicos |
| **RNID / RNPC** | Sistema externo | Registos nacionais |
| **SIG Nacional** | Sistema externo | Informação geográfica |
| **Sistema Contabilístico** | Sistema externo | ERP financeiro da Junta |
| **Gateway Pagamentos** | Sistema externo | Referências multibanco, MB Way |
| **SMS Gateway** | Sistema externo | Envio de SMS |
| **Email Gateway** | Sistema externo | Envio de email |
| **CNPD** | Entidade externa | Autoridade de protecção de dados |
| **DPO Interno** | Actor humano | Data Protection Officer |

### Fluxos Principais

| De | Para | Descrição | Protocolo |
|---|---|---|---|
| Cidadão | Plataforma | Submeter pedidos, consultar estado | HTTPS (Browser/API) |
| Funcionário | Plataforma | Gerir processos, emitir documentos | HTTPS (Browser) |
| Plataforma | CMD | Autenticar cidadão | OIDC |
| Plataforma | Autenticação.gov | Autenticar funcionário | SAML |
| Plataforma | SMS Gateway | Enviar notificações | API REST |
| Plataforma | Gateway Pagamentos | Gerar referências | API REST |

## Requisitos

- O sistema deve suportar todos os actores e sistemas externos identificados
- A comunicação com sistemas externos segue padrões de segurança definidos (TLS 1.3+)
- A falha de um sistema externo não deve bloquear a operação da plataforma (circuit breaker)

## Regras de Negócio

- A autenticação de cidadãos é obrigatória para submissão de pedidos
- Funcionários autenticam-se via Autenticação.gov ou credenciais internas
- Sistemas externos nacionais têm precedência sobre dados inseridos manualmente

## Critérios de Aceitação

- O diagrama de contexto está validado pelos stakeholders técnicos e de negócio
- Todas as integrações externas estão documentadas com detalhe técnico
- Os actores humanos estão mapeados para os casos de uso correspondentes

## Documentos Relacionados

- [Diagrama de Contentores](diagrama-de-contentores.md)
- [01 — Mapeamento de Atores](../01-analise-de-negocio/mapeamento-atores.md)
- [10 — Integrações](../10-integracoes/index.md)
- [10 — Autenticação Externa](../10-integracoes/autenticacao-externa.md)
