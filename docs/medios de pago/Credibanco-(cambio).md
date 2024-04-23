---
stoplight-id: q0tx49t56wklh
---

# Credibanco (cambio)

- Visa (CR_VS)
- AMEX (CR_AMEX)
- Diners (CR_DN)

Configuración general de los medios de pago

para credibanco hay 2 alternativas, si tenemos un certificado de credibanco podemos proporcionar el id y de no existir el certificado de credibanco debemos proporcionar la información requerida para crearlo

| Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  |
| 	pfxID | YES |	Identificador del certificado de credibanco exitente, este atributo se envía dentro del objeto "settings", solo es requerido si no se envían los campos para crear un certificado (username, password, retailCode, terminalNumber) | 12
| isEcommerce | YES| Propiedad de la request de la api que determina si es un comercio electrónico| true| |
| username | YES| usuario de la terminal, solo es requerido si no se envía el campo pfxID | userxx| |
| password | YES| contraseña de la terminal, solo es requerido si no se envía el campo pfxID| passwordxx| |
| retailCode | YES |  | 011211407 | Código único de venta no presente en la request este atributo se envía dentro del objeto "settings", solo es requerido si no se envía el campo pfxID | 
| terminalNumber | YES |	Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings", solo es requerido si no se envía el campo pfxID |

---------------------------------------------------

## Información por paises:

**Colombia**

Métodos de pago:

- Visa (CR_VS)
- AMEX (CR_AMEX)
- Diners (CR_DN)

Observaciones:

- Se debe configurar el certificado
- Si permite threeDS
- No se usan reglas de crédito

Bancos: (Escribir bancos disponibles)

- 

Ejemplo de objeto paymentMethod con certificado **no** existente:

```json
{
  "code": "CR_VS",
  "order": 3,
  "financialEntity": 16,
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "accountType": 1,
  "settings": {
      "username": "FIDUCOLDEX02",
      "password": "FIDUCOLDEX02",
      "retailCode": "011211407",
      "terminalNumber": "1234568",
      "isEcommerce": true
  },
  "threeDS": true
}
```

Ejemplo de objeto paymentMethod con certificado existente:

```json
{
  "code": "CR_VS",
  "order": 3,
  "financialEntity": 16,
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "accountType": 1,
  "settings": {
      "pfxID": 342,
      "isEcommerce": true
  },
  "threeDS": true
}
```

---------------------------------------------------