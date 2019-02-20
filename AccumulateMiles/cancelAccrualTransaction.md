---
layout: page
title: CancelAccrualTransaction
permalink: /accumulateMiles/cancelAccrualTransaction/
parent: AccumulateMiles
---
## CancelAccrualTransaction
API usada para cancelar uma transação acúmulo de milhas.

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
      <v2:CancelAccrualTransactionRequest>
         <v2:siebelTransactionId>1-1BD1F5V8</v2:siebelTransactionId>
         <v2:comments>Cancelar</v2:comments>
      </v2:CancelAccrualTransactionRequest>
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