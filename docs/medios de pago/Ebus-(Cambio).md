---
stoplight-id: 2j8llq15b5yu8
---

# Ebus (Cambio)

- Ebus Visa (EB_VS) 

- Ebus Amex (EB_AM) 

- Ebus Mastercard (EB_MC) 

- Ebus ATH (EBATH) 

- Ebus ATH Visa (EBATV) 

- Ebus ATH Mastercard (EBATM) 


| Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| accountNumber | YES | | 26546 |  |
| merchantCode | YES |  | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
| terminalNumber | YES |  | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |

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

------------------------------------------------------

Ejemplo de objeto paymentMethod:

```json
{
  "code": "EB_VS",
  "order": 3,
  "financialEntity": 16,
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "accountType": 1,
  "settings": {
      "terminalNumber": "1234568",
      "merchantCode": 71478293
      "isEcommerce": true
  },
  "threeDS": true
}
```