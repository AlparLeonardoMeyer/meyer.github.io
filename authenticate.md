---
layout: page
title: Autenticação
permalink: /authenticate/
nav_order: 3
---
## Autenticação
É usada o padrão OAuth para autenticação. A Smiles fornecerá um client_id e um client_secret usada para obter um token "Bearer" e este token será usado para a ivocação de todas as APIs da Smiles.

### URL
_/api/oauth/token_


### REQUEST

#### HEADERS

| KEY           | VALUE                             |
|:--------------|:----------------------------------|
| Channel       | PARTNER                           |
| Content-Type  | application/x-www-form-urlencoded |

#### BODY
```
grant_type=client_credentials&client_id=[client_id]&client_secret=[client_secret]
```

### RESPONSE 

#### BODY
```json
{
    "scope": "PUT_/api/checkout PUT_/api/favorite/passengers PUT_/api/members/flights/seats PUT_/api/members/membership",
    "expires_in": 3599,
    "token_type": "Bearer",
    "access_token": "W0z3X4rhTwNYzuteSH0f1b7eUztEZLFhXTUVrrWj8HZe2NCsXgEX6b"
}
```

### Códigos de Erros

| Código       | Resposta                      | Ação                                                        |
|:-------------|:------------------------------|:------------------------------------------------------------|
| 1            | Ocorreu um erro técnico       | Contacte a Smiles                                           |
| 6            | Parâmetro de entrada inválido | Verifique o seu request e os parâmetros obrigatórios da API |
