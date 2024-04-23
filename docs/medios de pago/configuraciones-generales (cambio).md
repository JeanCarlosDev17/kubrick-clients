---
stoplight-id: izjtajorwlyk4
---

# Configuraciones generales (cambio)

Este apartado indica los campos que tienen en común todos los medios de pago.

| Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| code | YES | Propiedad de la request de la api que determina el medio de pago | CR_VS |
| comissionModel | NO |  | F |  |
| comissionValue | NO |  | 2.5 |  |
| accountNumber | NO |  | 1234567811 |  |
| financialEntity | YES |  | 16 |  |
| accountType | NO |  | 1 | Sus valores posibles son 1, 2 y 3, donde 1 representa SAVINGS (Ahorros), 2 representa CURRENT (Corriente), y 3 representa CREDIT CARD (Tarjeta de crédito) | 
| isEcommerce | N |  | true | En la request, este atributo se envía dentro del objeto "settings" | 
| threeDS | YES |  | true |  | 

# Categorías de los medios de pago

