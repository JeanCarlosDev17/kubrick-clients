---
stoplight-id: bz6ie8ssi7eqq
---

# Credibanco

- Visa (CR_VS)
- AMEX (CR_AMEX)
- Diners (CR_DN)

Configuración general de los medios de pago

para credibanco hay 2 alternativas, si tenemos un certificado de credibanco podemos proporcionar el id y de no existir el certificado de credibanco debemos proporcionar la información requerida para crearlo


Caso con certificado creado

| Field Name| Required  | Description | Example | Observations |
 ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago | CR_VS |
| order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| comissionValue | NO |  | 2.5 |  |
| Número de cuenta | accountNumber | NO | | 26546 |  |
| accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| pfxID | YES |	Identificador del certificado de credibanco exitente, este atributo se envía dentro del objeto "settings" | 12
| isEcommerce | YES| Propiedad de la request de la api que determina si es un comercio electrónico| true| |
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

---------------------------------------------------

**Caso sin certificado existente**



| Name in panel | Name in API | Required  | Description | Example | Observations |
| ------------- | ----------- | --------- | ----------- | ------- | ------------ |
| Entidad financiera | financialEntity | YES |  | 16 |  |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago | CR_VS |
| Prioridad | Order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| Modelo de comisión | comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| Comisión | comissionValue | NO |  | 2.5 |  |
| Número de cuenta | accountNumber | NO | | 26546 |  |
| Tipo de cuenta | accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| Usuario | username | YES| usuario de la terminal| userxx| |
| Contraseña | password | YES| contraseña de la terminal| passwordxx| |
| Código único | retailCode | YES |  | 011211407 | Código único de venta no presente en la request este atributo se envía dentro del objeto "settings" | 
| Número de terminal | terminalNumber | YES |	Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| Comercio electrónico | isEcommerce | YES| Propiedad de la request de la api que determina si es un comercio electrónico| true| |
| N/A | threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

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

