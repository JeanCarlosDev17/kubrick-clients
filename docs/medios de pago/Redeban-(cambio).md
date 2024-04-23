---
stoplight-id: 1am2f49u4rkq5
---

# Redeban (cambio)

- Mastercard (RM_MC)

| Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| retailCode | YES |  | 011211407 | Código único de venta no presente En la request este atributo se envía dentro del objeto "settings" | 
| terminalNumber | YES | 	Terminal en la que procesa el comercio en la red | 1277723 | En la request, este atributo se envía dentro del objeto "settings" |
| terminalLocation | YES | 	 | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |


---------------------------------------------------

## Información por paises:

**Colombia**

Métodos de pago:

- Mastercard (RM_MC)

Observaciones:

- No se debe configurar el certificado
- Si permite threeDS
- No se usan reglas de crédito

Bancos: (Escribir bancos disponibles)

- 

Ejemplo de objeto paymentMethod:

```json
{
  "code": "RM_MC",
  "order": 3,
  "financialEntity": 16,
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "accountType": 1,
  "settings": {
      "retailCode": "011211407",
      "terminalNumber": "1234568",
      "terminalLocation": "Medellin",
      "isEcommerce": true
  },
  "threeDS": true
}
```