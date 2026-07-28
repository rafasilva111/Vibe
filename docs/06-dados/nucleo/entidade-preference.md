# Preference

## Descrição
Preferências de utilizador.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| utilizador_id | UUID (FK) | Utilizador |
| chave | String | Nome da preferência |
| valor | JSON | Valor |
