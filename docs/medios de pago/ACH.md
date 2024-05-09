---
stoplight-id: 5k3unmux2vm18
---

# ACH

-  "_"PSE"_"

Configuración general de los medios de pago

| Name in panel | Name in API | Required  | Description | Example | Observations |
| ------------- | ----------- | --------- | ----------- | ------- | ------------ |
| Entidad financiera | financialEntity | YES |  | 16 |  |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago | CR_VS |
| Prioridad | Order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| Modelo de comisión | comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| Comisión | comissionValue | NO |  | 2.5 |  |
| Número de cuenta | accountNumber | NO | | 26546 |  |
| Tipo de cuenta | accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| Código de entidad | entityCode | YES | Código generado por el comercio en la plataforma de ACH financiera | 9002992280 |  |
| Código de servicio | serviceCode | YES | Código generado por el comercio en la plataforma de ACH | 001 |  |

---------------------------------------------------

## Información por paises:

**Colombia**

Métodos de pago:

- PSE

Observaciones:

- No se debe configurar el certificado
- No permite threeDS
- No se usan reglas de crédito

Bancos: (Escribir bancos disponibles)

- 

Ejemplo objeto paymentMethod:

```json
{
  "code": "PSE",
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "financialEntity": 16,
  "accountType": 1,
  "settings": {
      "terminalNumber": "1234568",
      "terminalLocation": "Medellin",
      "merchantCode": "2002",
      "entityCode": "9002992280",
      "serviceCode": "123654",
      "isEcommerce": true
  },
  "threeDS": false
}
```

---------------------------------------------------

