---
stoplight-id: gw9l6jz5gwzbz
---

# Paystudio (Cambio)

- PayStudio Mastercard (PS_MC)
- PayStudio Visa (PS_VS)
- PayStudio Amex (PS_AM)
- PayStudio Maestro (PS_MS)

| Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| Order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| merchantCode | YES | Código que representa al comercio en la red | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
| terminalNumber | YES | 	Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| creditRules | YES ||| [example](reference/Kubrick.json/components/schemas/creditRules) || 

---------------------------------------------------
## Información por paises:

**Chile** (Laura Calle)

Métodos de pago:

- Mastercard (PS_MC)
- Visa (PS_VS)
- Maestro (PS_MS)
- AMEX (PS_AMEX)

Observaciones:

- Si permite threeDS
- Solo admite transacciones con peso chileno (CLP)

Bancos:

- Getnet

------------------------------------------------------

**Uruguay**

Métodos de pago:

- Mastercard (PS_MC)
- Visa (PS_VS)
- Maestro (PS_MS)

Observaciones:

- Si permite threeDS (En micrositios si, en el resto de MP no sabrías) (Validar con ST)
- Solo admite transacciones con peso chileno (UYU) y dólar (USD)

Bancos:

- Banco Santander (A través de Getnet)

------------------------------------------------------

Ejemplo de objeto paymentMethod:

```json
{
  "code": "PS_MC",
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
  "threeDS": true,
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
