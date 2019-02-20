---
layout: page
title: GetAccrualTransaction
permalink: /accumulateMiles/getAccrualTransaction/
parent: AccumulateMiles
---
## GetAccrualTransaction
API usada para buscar uma transação acúmulo de milhas.

### URL
_/smiles-bus/Services/AccumulateMilesV2_


### REQUEST

#### HEADERS

| KEY           | VALUE                             |
|:--------------|:----------------------------------|
| Content-Type  | text/xml                          |
| Authorization | Bearer + _access_token_           |

#### BODY
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:v1="http://www.smiles.com.br/EBO/Common/V1" xmlns:v2="http://www.smiles.com.br/Services/AccumulateMiles/V2">
   <soapenv:Header>
      <v1:SmilesHeader>
         <v1:channel>PARTNER</v1:channel>
      </v1:SmilesHeader>
   </soapenv:Header>
   <soapenv:Body>
      <v2:GetAccrualTransactionRequest>
         <v2:partnerAlias>GRA</v2:partnerAlias>
         <v2:soaTransactionId>1535744147988540501ec4b4f4444a</v2:soaTransactionId>
         <v2:partnerTransactionId>650101067</v2:partnerTransactionId>
      </v2:GetAccrualTransactionRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

### RESPONSE 

#### BODY
```xml
<soapenv:Envelope xmlns:env="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/">
   <env:Header xmlns:v1="http://www.smiles.com.br/EBO/Common/V1" xmlns:v2="http://www.smiles.com.br/Services/AccumulateMiles/V2">
      <v1:SmilesHeader>
         <v1:channel>PARTNER</v1:channel>
      </v1:SmilesHeader>
   </env:Header>
   <env:Body xmlns:v1="http://www.smiles.com.br/EBO/Common/V1" xmlns:v2="http://www.smiles.com.br/Services/AccumulateMiles/V2">
      <pra:ProcessAccrualResponse xmlns:pra="http://www.smiles.com.br/Services/AccumulateMiles/V2">
         <pra:soaTransactionId>1550614106240228e1cb3c9d9da34d</pra:soaTransactionId>
         <pra:errorCode>00</pra:errorCode>
         <pra:errorDescription>SUCCESS</pra:errorDescription>
      </pra:ProcessAccrualResponse>
   </env:Body>
</soapenv:Envelope>
```

### Códigos de Erros

| Código       | Resposta                      | Ação                                                        |
|:-------------|:------------------------------|:------------------------------------------------------------|
| 1            | Ocorreu um erro técnico       | Contacte a Smiles                                           |
| 6            | Parâmetro de entrada inválido | Verifique o seu request e os parâmetros obrigatórios da API |