---
stoplight-id: 5wzobd3z1rl58
---

<!--
type: tab
title: ACH(PSE)
-->

# ACH(PSE)

-  \_PSE_


Configuración general de los medios de pago

| Field Name | Required  | Description | Example | Observations |
 ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  || N/A| code | YES | Propiedad de la request de la api que determina el medio de pago | \_PSE_ |
| Order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| comissionValue | NO |  | 2.5 |  |
| accountNumber | NO | | 26546 |  |
| accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| entityCode | YES | Usualmente es el nit o la identificación de la empresa | 9002992280 | |
| serviceCode | YES | Código generado por el comercio en la plataforma de ACH | 001 ||
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

---------------------------------------------------

## Información por paises:

**Colombia**

Métodos de pago:

-  \_PSE_

Observaciones:

- No se debe configurar el certificado
- No permite threeDS
- No se usan reglas de crédito

Ejemplo objeto paymentMethod:

```json
{
  "code": "_PSE_",
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "financialEntity": 16,
  "accountType": 1,
  "settings": {
      "entityCode": "170892",
      "serviceCode": "15916855-8"
      "isEcommerce": true
  },
  "threeDS": false
}
```
<!--
type: tab
title: ATH(Efectivo) Colombia
-->
# ATH(Efectivo) Colombia

-  \_ATH_


Configuración general de los medios de pago

| Field Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  || N/A| code | YES | Propiedad de la request de la api que determina el medio de pago | \_ATH_ |
| order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| comissionValue | NO |  | 2.5 |  |
| accountNumber | NO | | 26546 |  |
| accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| agreement | YES | | 64654| |
| agreementName | YES | |"mi convenio" | |
| iacCode | YES | | 4456464| |
| acceptChecks | NO | | true| |
| disableBlocks | NO | | ath_cajas_exito, ath_efecty | Escriba uno o más nombres de bloque separado por comas, los bloques disponibles son: ath_baloto, ath_corresponsales, ath_cajas_exito, ath_efecty, ath_cajeros, ath_supergiros |
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |


---------------------------------------------------

## Información por paises:

**Colombia**

Métodos de pago:

-  \_ATH_

Observaciones:

- No permite threeDS
- No se usan reglas de crédito

Ejemplo objeto paymentMethod:

```json
{
  "code": "_ATH_",
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "financialEntity": 16,
  "accountType": 1,
  "settings": {
    "agreement":64654,
    "agreementName":"mi convenio",
    "iacCode":4456464,
    "acceptChecks": true,
    "disableBlocks": "ath_efecty, ath_cajeros"
  },
  "threeDS": false
}
```

---------------------------------------------------

<!--
type: tab
title: Botón Bancolombia
-->

# Botón Bancolombia

-  BTNBC


Configuración general de los medios de pago

| Name in panel | Name in API | Required  | Description | Example | Observations |
| ------------- | ----------- | --------- | ----------- | ------- | ------------ |
| Entidad financiera | financialEntity | YES |  | 16 |  |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago | BTNBC |
| Prioridad | Order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| Modelo de comisión | comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| Comisión | comissionValue | NO |  | 2.5 |  |
| Número de cuenta | accountNumber | NO | | 26546 |  |
| Tipo de cuenta | accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| Hash | hash | YES | Código que identifica el botón de transferencia del comercio | 9002992280 | |
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

---------------------------------------------------

## Información por paises:

**Colombia**

Métodos de pago:

-  BTNBC

Observaciones:

- No permite threeDS
- No se usan reglas de crédito

Ejemplo objeto paymentMethod:

```json
{
  "code": "BTNBC",
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "financialEntity": 16,
  "accountType": 1,
  "settings": {
    "hash": "h4ShG3NER1C",
  },
  "threeDS": false
}
```

---------------------------------------------------


<!--
type: tab
title: Credibanco
-->

# Credibanco

- Visa (CR_VS)
- AMEX (CR_AMEX)
- Diners (CR_DN)

Configuración general de los medios de pago

Para credibanco hay 2 alternativas, si tenemos un certificado de credibanco podemos proporcionar el id y de no existir el certificado de credibanco debemos proporcionar la información requerida para crearlo


Caso con certificado creado

| Field Name| Required  | Description | Example | Observations |
 ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  |
| code | YES | Propiedad de la request de la api que determina el medio de pago | CR_VS |
| order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| comissionValue | NO |  | 2.5 |  |
| accountNumber | NO | | 26546 |  |
| accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| pfxID | YES |	Identificador del certificado de credibanco exitente, este atributo se envía dentro del objeto "settings" | 12
| isEcommerce | YES| Propiedad de la request de la api que determina si es un comercio electrónico| true| |
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

---------------------------------------------------

**Caso sin certificado existente**



| Field Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  |
| code | YES | Propiedad de la request de la api que determina el medio de pago | CR_VS |
| order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| comissionValue | NO |  | 2.5 |  |
| accountNumber | NO | | 26546 |  |
| accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| username | YES| usuario de la terminal| userxx| |
| password | YES| contraseña de la terminal| passwordxx| |
| retailCode | YES |  | 011211407 | Código único de venta no presente en la request este atributo se envía dentro del objeto "settings" | 
| terminalNumber | YES |	Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| isEcommerce | YES| Propiedad de la request de la api que determina si es un comercio electrónico| true| |
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

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


<!--
type: tab
title: Ebus
-->
# Ebus

- Ebus Visa (EB_VS) 

- Ebus Amex (EB_AM) 

- Ebus Mastercard (EB_MC) 

- Ebus ATH (EBATH) 

- Ebus ATH Visa (EBATV) 

- Ebus ATH Mastercard (EBATM) 


Configuración general de los medios de pago
| Field Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  |
| code | YES | Propiedad de la request de la api que determina el medio de pago | EB_AM|
| Prioridad | order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| comissionValue | NO |  | 2.5 |  |
| accountNumber | YES | | 26546 |  |
| accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| merchantCode | YES |  | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
| terminalNumber | YES |  | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| username  | YES | Usuario que identifica el login del comercio | 2002 | En la request, este atributo se envía dentro del objeto "settings" |
| password | YES | Metodo de seguridad para identificar al comercio | 2002 | En la request, este atributo se envía dentro del objeto "settings" |
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |
| creditRules | NO ||| '{creditRules: "mirule"}'|| 


---------------------------------------------------
Información por paises:

**Puerto Rico**



Métodos de pago:
- Ebus Visa (EB_VS) 

- Ebus Amex (EB_AM) 

- Ebus Mastercard (EB_MC) 

- Ebus ATH (EBATH) 

- Ebus ATH Visa (EBATM) 

- Ebus ATH Mastercard (EBATV) 


Observaciones:
- Si permite threeDS
- Solo admite transacciones con dólar (USD)


Configuraciones especificas por banco:

- Banco popular
  - Al merchantCode se le antepone el número 4549 
- FirstBank 
  - Al merchantCode se le antepone el número 7147

Ejemplo de objeto paymentMethod con certificado existente:

```json
{
  "code": "EB_AM",
  "order": 3,
  "financialEntity": 16,
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "accountType": 1,
  "settings": {
      "username": "myusername",
      "password": "password_",
      "terminalNumber": "1734585",
      "merchantCode": "2009",
      "serviceCode": "123657",
      "isEcommerce": true
  },
  "creditRules": {
      "include": [
          {
              "max": 60,
              "min": 1,
              "active": true,
              "region": [
                  "on_us",
                  "local"
              ],
              "subType": "02",
              "cardType": [
                  "credit"
              ],
              "currency": [
                  "USD"
              ],
              "interest": 0,
              "salePlan": "02"
          }
      ]
  },
  "threeDS": true
}
```
------------------------------------------------------

<!--
type: tab
title: Redeban
-->



> 

<!-- type: tab-end -->