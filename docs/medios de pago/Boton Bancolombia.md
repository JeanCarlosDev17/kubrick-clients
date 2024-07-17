---
stoplight-id: loc71szb7mmpy
---

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

- No se debe configurar el certificado
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

