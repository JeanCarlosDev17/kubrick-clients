---
stoplight-id: keqkna3lwe7qd
---

# Transerver (cambio)

- Mastercard (TS_MC)
- Visa (TS_VS)

| Name | Required  | Description | Example | Observations |
| --------- | --------- | ----------- | ------- | ------------ |
|forceConversionCurrency| YES | Define la moneda del medio de pago | USD | En la request, este atributo se envía dentro del objeto "settings" |
| merchantCode | YES | Código que representa al comercio en la red | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
| terminalNumber | YES | Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |

---------------------------------------------------

Información por paises:

**Costa Rica**

Métodos de pago:

- Mastercard (TS_MC)
- Visa (TS_VS)
- Puntos transerver

Observaciones:

- Si permite threeDS
- Solo admite transacciones con dólar (USD) o Colón costarricense (CRC)
- Usa reglas de crédito
- Se crea un sitio por moneda
- Se debe forzar la moneda

Bancos:

- Banco de Costa Rica (BCR)
- Davivienda Costa Rica

Ejemplo de objeto paymentMethod:

```json
{
  "code": "TS_MC",
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "financialEntity": 16,
  "accountType": 1,
  "settings": {
        "forceConversionCurrency": "USD",
        "terminalNumber": "1234568",
        "merchantCode": "2002",
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
                    "CLP"
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