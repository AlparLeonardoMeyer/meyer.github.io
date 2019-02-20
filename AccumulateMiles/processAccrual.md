---
layout: page
title: ProcessAccrual
permalink: /accumulateMiles/processAccrual/
parent: AccumulateMiles
---
## ProcessAccrual
API usada para processar um acúmulo de milhas para um usuário.

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
    <v1:SmilesHeader xmlns:v1="http://www.smiles.com.br/EBO/Common/V1">
      <v1:channel>PARTNER</v1:channel>
    </v1:SmilesHeader>
  </soapenv:Header>
  <soapenv:Body>
    <v2:ProcessAccrualRequest xmlns:v2="http://www.smiles.com.br/Services/AccumulateMiles/V2">
      <v2:memberCPF>30617509832</v2:memberCPF> <!-- CPF do usuário que receberá as milhas -->
      <v2:transactionDate>2018-07-04T09:40:49.000</v2:transactionDate> <!-- Data da transação -->
      <v2:amount>200</v2:amount> <!-- Quantidade de milhas a ser acumulada -->
      <v2:productName>Créditos do Banco do Estado do Pará</v2:productName> <!-- Nome do produto (enviado pela Smiles) -->
      <v2:comments>8709</v2:comments> <!-- Um comentário qualquer sobre esta transação -->
      <v2:partnerAlias>BAN</v2:partnerAlias> <!-- Código do parceiro (enviado pela Smiles) -->
      <v2:partnerTransactionId>8842604-V</v2:partnerTransactionId> <!-- Este é um alphanumérico único que identifique a transação do lado do parceiro -->
    </v2:ProcessAccrualRequest>
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