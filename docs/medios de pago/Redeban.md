---
stoplight-id: txwr6bx9p73b6
---

# Redeban

- Mastercard (RM_MC)

Configuración general de los medios de pago

| Name in panel | Name in API | Required  | Description | Example | Observations |
| ------------- | ----------- | --------- | ----------- | ------- | ------------ |
| Entidad financiera | financialEntity | YES |  | 16 |  |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago | RM_MC |
| Prioridad | order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| Modelo de comisión | comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| Comisión | comissionValue | NO |  | 2.5 |  |
| Número de cuenta | accountNumber | NO | | 26546 |  |
| Tipo de cuenta | accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| Código único | retailCode | YES |  | 011211407 | Código único de venta no presente En la request este atributo se envía dentro del objeto "settings" | 
| Número de terminal | terminalNumber | YES | 	Terminal en la que procesa el comercio en la red | 1277723 | En la request, este atributo se envía dentro del objeto "settings" |
| Nombre y ubicación | terminalLocation | YES | 	 | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| N/A | threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

---------------------------------------------------

## Información por paises:

**Colombia**

Métodos de pago:

- Mastercard (RM_MC)

Observaciones:

- No se debe configurar el certificado
- Si permite threeDS
- No se usan reglas de crédito

Bancos: (Escribir bancos disponibles)

- 

Ejemplo de objeto paymentMethod:

```json
{
  "code": "RM_MC",
  "order": 3,
  "financialEntity": 16,
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "accountType": 1,
  "settings": {
      "retailCode": "011211407",
      "terminalNumber": "1234568",
      "terminalLocation": "Medellin",
      "isEcommerce": true
  },
  "threeDS": true
}
```

---------------------------------------------------
