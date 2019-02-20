---
layout: page
title: CreateSimplifiedMember
permalink: /member/createSimplifiedMember/
parent: Member
---
## CreateSimplifiedMember
API usada para criar um usuário com o mínimo de dados possível.

### URL
_/smiles-bus/MemberV1/createSimplifiedMember_


### REQUEST

#### HEADERS

| KEY           | VALUE                             |
|:--------------|:----------------------------------|
| Content-Type  | text/xml                          |
| Authorization | Bearer + _access_token_           |

#### BODY
```xml
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  xmlns:WL5G3N1="http://www.smiles.com.br/Services/Member/V1" xmlns:WL5G3N2="http://www.smiles.com.br/EBO/Common/V1" xmlns:comebo="http://www.smiles.com.br/EBO/Common/V1" xmlns:ebm="http://www.smiles.com.br/Services/Member/V1">
	<soap:Header/>
	<soap:Body>
		<WL5G3N1:createSimplifiedMemberRequest xmlns:WL5G3N1="http://www.smiles.com.br/Services/Member/V1" xmlns="http://www.smiles.com.br/Services/Member/V1">
			<WL5G3N1:firstName>Ja</WL5G3N1:firstName>
			<WL5G3N1:lastName>Ja</WL5G3N1:lastName>
			<WL5G3N1:documentList>
				<ebm:document xmlns:ebm="http://www.smiles.com.br/Services/Member/V1">
					<comebo:number xmlns:comebo="http://www.smiles.com.br/EBO/CommonEBO/V1">04740012022</comebo:number>
					<comebo:type xmlns:comebo="http://www.smiles.com.br/EBO/CommonEBO/V1">CPF</comebo:type>
				</ebm:document>
				<ebm:document xmlns:ebm="http://www.smiles.com.br/Services/Member/V1">
					<comebo:number xmlns:comebo="http://www.smiles.com.br/EBO/CommonEBO/V1">000000000</comebo:number>
					<comebo:type xmlns:comebo="http://www.smiles.com.br/EBO/CommonEBO/V1">RG</comebo:type>
				</ebm:document>
			</WL5G3N1:documentList>
			<ebm:electronicAddressList xmlns:ebm="http://www.smiles.com.br/Services/Member/V1">
				<ebm:email>
					<comebo:address xmlns:comebo="http://www.smiles.com.br/EBO/CommonEBO/V1">testeparceiro@smiles.com.br</comebo:address>
				</ebm:email>
			</ebm:electronicAddressList>
			<ebm:birthDate xmlns:ebm="http://www.smiles.com.br/Services/Member/V1">2000-03-26</ebm:birthDate>
			<ebm:gender xmlns:ebm="http://www.smiles.com.br/Services/Member/V1">MALE</ebm:gender>
			<ebm:addressList xmlns:ebm="http://www.smiles.com.br/Services/Member/V1">
				<ebm:address>
					<comebo:type xmlns:comebo="http://www.smiles.com.br/EBO/CommonEBO/V1">PERSONAL</comebo:type>
				</ebm:address>
			</ebm:addressList>
			<ebm:partner xmlns:ebm="http://www.smiles.com.br/Services/Member/V1">SHE</ebm:partner>
			<ebm:channel xmlns:ebm="http://www.smiles.com.br/Services/Member/V1">PARTNER</ebm:channel>
		</WL5G3N1:createSimplifiedMemberRequest>
	</soap:Body>
</soap:Envelope>
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

| Código    | Resposta                          | Ação                                                        |
|:----------|:----------------------------------|:------------------------------------------------------------|
| 1         | Ocorreu um erro técnico           | Contacte a Smiles                                           |
| 6         | Parâmetro de entrada inválido     | Verifique o seu request e os parâmetros obrigatórios da API |
| 12        | Erro no envio do email            | Contacte a Smiles                                           |
| 13        | Erro na geracao da resposta       | Contacte a Smiles                                           |
| 20        | Erro ao criar membro              | Contacte a Smiles                                           |
| 22        | CPF já cadastrado anteriormente   | CPF cadastrado já consta na base de dados da Smiles.        |
| 26        | Email já cadastrado anteriormente | Email cadastrado já consta na base de dados da Smiles.      |
| 54        | Partner Inválido                  | Partner enviado é inválido. Contacte a Smiles               |
| 55        | Channel Inválido                  | Channel enviado é inválido. Contacte a Smiles               |
| 56        | CEP Inválido                      | CEP enviado é inválido. Contacte a Smiles                   |