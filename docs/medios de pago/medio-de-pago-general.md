---
stoplight-id: ci54f9cn1h0an
---

# Medio de pago general

| Name in panel | Name in API | Required  | Description | Example | Observations |
| ------------- | ----------- | --------- | ----------- | ------- | ------------ |
| N/A| code | YES | Propiedad de la request de la api que determina el medio de pago | CR_VS |
| Modelo de comisión | comissionModel | YES |  | F |  |
| Comisión | comissionValue | YES |  | 2.5 |  |
| Número de cuenta | accountNumber | YES |  | 1234567811 |  |
| Entidad financiera | financialEntity | YES |  | 16 |  |
| Tipo de cuenta | accountType | YES |  | 1 | Sus valores posibles son 1, 2 y 3, donde 1 representa SAVINGS(Ahorros), 2 representa CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| Número de terminal | terminalNumber | YES |  | 1234568 | En la request, este atributo se envía dentro del objeto "settings" | 
|  | terminalLocation | YES |  | Medellin | En la request, este atributo se envía dentro del objeto "settings" | 
| Código de entidad | merchantCode | YES |  | 2002 | En la request, este atributo se envía dentro del objeto "settings" | 
|  | serviceCode | YES |  | 123654 | En la request, este atributo se envía dentro del objeto "settings" | 
|  | isEcommerce | YES |  | true | En la request, este atributo se envía dentro del objeto "settings" | 
|  | forceConversionCurrency | YES |  | USD |  | 
| Reglas de tipo de crédito | creditRules | NO |  | [example](reference/Kubrick.json/components/schemas/creditRules) |  | 
| N/A | threeDS | YES |  | true |  | 