# PayStudio

- PayStudio Mastercard (PS_MC)
- PayStudio Visa (PS_VS)
- PayStudio Amex (PS_AM)
- PayStudio Maestro (PS_MS)


Configuración general de los medios de pago
| Name in panel | Name in API | Required  | Description | Example | Observations |
| ------------- | ----------- | --------- | ----------- | ------- | ------------ |
| Entidad financiera | financialEntity | YES |  | 16 |  |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago |PS_VS|
| Prioridad | Order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| Modelo de comisión | comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| Comisión | comissionValue | NO |  | 2.5 |  |
| Número de cuenta | accountNumber | NO | | 26546 |  |
| Tipo de cuenta | accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| Código de entidad | merchantCode | YES | Código que representa al comercio en la red | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
| Número de terminal | terminalNumber | YES | 	Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| N/A | threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |
| Reglas de crédito | creditRules | YES ||| [example](reference/Kubrick.json/components/schemas/creditRules) || 


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
