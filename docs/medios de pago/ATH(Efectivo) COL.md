---
stoplight-id: z9mzc44ujkb6b
---

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

