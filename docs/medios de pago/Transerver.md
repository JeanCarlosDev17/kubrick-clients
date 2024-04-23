# Transerver

- Mastercard (TS_MC)
- Visa (TS_VS)


Configuración general de los medios de pago
| Name in panel | Name in API | Required  | Description | Example | Observations |
| ------------- | ----------- | --------- | ----------- | ------- | ------------ |
| Entidad financiera | financialEntity | YES |  | 16 |  |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago |TS_VS|
| Prioridad | Order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| Modelo de comisión | comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| Comisión | comissionValue | NO |  | 2.5 |  |
| Número de cuenta | accountNumber | NO | | 26546 |  |
| Tipo de cuenta | accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| Código de entidad | merchantCode | YES | Código que representa al comercio en la red | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
| Número de terminal | terminalNumber | YES | Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| N/A | threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |
| Reglas de crédito | creditRules | NO ||| [example](reference/Kubrick.json/components/schemas/creditRules)|| 
| |forceConversionCurrency| YES | Define la moneda del medio de pago | USD | En la request, este atributo se envía dentro del objeto "settings" |

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
        "terminalNumber": "1234568",
        "terminalLocation": "Medellin",
        "merchantCode": "2002",
        "serviceCode": "123654",
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

