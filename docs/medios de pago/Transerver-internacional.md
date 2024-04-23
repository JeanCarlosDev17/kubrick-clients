---
stoplight-id: ri431aduoiv8y
---

# Transerver internacional

- Mastercard (TSIMC)
- Visa (TSIVS)
- Tarjeta clave (VALIDAR Y ACTUALIZAR EN KUBRICK)

Configuración general de los medios de pago

| Name in panel | Name in API | Required  | Description | Example | Observations |
| ------------- | ----------- | --------- | ----------- | ------- | ------------ |
| Entidad financiera | financialEntity | YES |  | 16 |  |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago |TSIVS|
| Prioridad | Order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| Modelo de comisión | comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| Comisión | comissionValue | NO |  | 2.5 |  |
| Número de cuenta | accountNumber | NO | | 26546 |  |
| Tipo de cuenta | accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| Forzar conversión de moneda | forceConversionCurrency | YES |  | HNL | En la request, este atributo se envía dentro del objeto "settings" | 
| Código de entidad | merchantCode | YES | Código que representa al comercio en la red | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
| Número de terminal | terminalNumber | YES | Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| N/A | threeDS | YES | Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS | true |  | 
| Reglas de crédito | creditRules | YES ||| [example](reference/Kubrick.json/components/schemas/creditRules) || 

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
- Tarjeta clave (Solo para Caja de ahorros y se debe investigar funcionamiento y añadir a Kubrick) (Lo maneja telered)

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

Ejemplo de objeto paymentMethod sin reglas de crédito:

```json
{
  "code": "TSIMC",
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
    "threeDS": true
}
```

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

