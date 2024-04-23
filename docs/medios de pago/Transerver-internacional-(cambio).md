---
stoplight-id: 979ryb21qke2u
---

# Transerver internacional (cambio)

- Mastercard (TSIMC)
- Visa (TSIVS)
- Tarjeta clave

| Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| forceConversionCurrency | YES |  | HNL | En la request, este atributo se envía dentro del objeto "settings" | 
| merchantCode | YES | Código que representa al comercio en la red | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
| terminalNumber | YES | Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| creditRules | YES ||| [example](reference/Kubrick.json/components/schemas/creditRules) || 

---------------------------------------------------

## Información por paises:

**Honduras**

Métodos de pago:

- Mastercard (TSIMC)
- Visa (TSIVS)

Observaciones:

- Si permite threeDS
- Solo admite transacciones con dólar (USD) o lempiras (HNL)
- Solo se admite una moneda por sitio, es decir, si se requiere pagar con mas de un tipo de moneda, se debe crear mas de un sitio
- Se debe forzar la moneda
- Se usan reglas de crédito (Para cuando un pago con TC se va a diferir a varias cuotas)

Bancos:

- Banco Atlantida

---------------------------------------------------

**Panamá**

Métodos de pago:

- Mastercard (TSIMC)
- Visa (TSIVS)
- Tarjeta clave (Solo para Caja de ahorros y se debe investigar funcionamiento y añadir a Kubrick) (Lo gesstiona telered)

Observaciones:

- Solo permite threeDS en Multibank y Caja de ahorros (Solo para MC y VS)
- Solo admiten transacciones con dólar (USD)
- No usan reglas de crédito 

Bancos:
 
- Multibank
- Towerbank
- Caja de ahorros

---------------------------------------------------

**Bélice**

Métodos de pago:

- Mastercard (TSIMC)
- Visa (TSIVS)

Observaciones:

- Si permite threeDS
- Solo admiten transacciones con dólar beliceño (BZD)
- Se debe forzar la moneda
- No se usan reglas de crédito

Bancos:

- Atlantic bank

--------------------------------------------------------

Ejemplo de objeto paymentMethod con reglas de crédito:

```json
{
  "code": "TSIMC",
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