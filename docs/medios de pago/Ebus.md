---
stoplight-id: 5chhh0czyhbny
---

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

