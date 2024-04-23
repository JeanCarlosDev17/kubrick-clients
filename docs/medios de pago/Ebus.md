---
stoplight-id: 5chhh0czyhbny
---

# Ebus

- Ebus Visa (EB_VS) 

- Ebus Amex (EB_AM) 

- Ebus Mastercard (EB_MC) 

- Ebus ATH (EBATH) 

- Ebus ATH Visa (EBATV) 

- Ebus ATH Mastercard (EBATM) 


Configuración general de los medios de pago
| Name in panel | Name in API | Required  | Description | Example | Observations |
| ------------- | ----------- | --------- | ----------- | ------- | ------------ |
| Entidad financiera | financialEntity | YES |  | 16 |  |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago |TS_VS|
| Prioridad | order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| Modelo de comisión | comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| Comisión | comissionValue | NO |  | 2.5 |  |
| Número de cuenta | accountNumber | YES | | 26546 |  |
| Tipo de cuenta | accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| Código de entidad | merchantCode | YES |  | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
| Número de terminal | terminalNumber | YES |  | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| Nombre de usuario  | username  | YES | Usuario que identifica el login del comercio | 2002 | En la request, este atributo se envía dentro del objeto "settings" |
| Contraseña  | password | YES | Metodo de seguridad para identificar al comercio | 2002 | En la request, este atributo se envía dentro del objeto "settings" |
| N/A | threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |
| Reglas de crédito | creditRules | NO ||| '{creditRules: "mirule"}'|| 


---------------------------------------------------
Información por paises:

**Puerto Rico**



Métodos de pago:
- Ebus Visa (EB_VS) 

- Ebus Amex (EB_AM) 

- Ebus Mastercard (EB_MC) 

- Ebus ATH (EBATH) 

- Ebus ATH Visa (EBATM) 

- Ebus ATH Mastercard (EBATV) 


Observaciones:
- Si permite threeDS
- Solo admite transacciones con dólar (USD)


Configuraciones especificas por banco:

- Banco popular
  - Al merchantCode se le antepone el número 4549 
- FirstBank 
  - Al merchantCode se le antepone el número 7147
------------------------------------------------------

