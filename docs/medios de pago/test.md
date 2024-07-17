---
stoplight-id: u5xcdr2uj774r
---

<!--
type: tab
title: ACH(PSE)
-->

# ACH(PSE)

-  \_PSE_


Configuración general de los medios de pago

| Field Name | Required  | Description | Example | Observations |
 ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  || N/A| code | YES | Propiedad de la request de la api que determina el medio de pago | \_PSE_ |
| Order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| comissionValue | NO |  | 2.5 |  |
| accountNumber | NO | | 26546 |  |
| accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| entityCode | YES | Usualmente es el nit o la identificación de la empresa | 9002992280 | |
| serviceCode | YES | Código generado por el comercio en la plataforma de ACH | 001 ||
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

---------------------------------------------------

## Información por paises:

**Colombia**

Métodos de pago:

-  \_PSE_

Observaciones:

- No se debe configurar el certificado
- No permite threeDS
- No se usan reglas de crédito

Ejemplo objeto paymentMethod:

```json
{
  "code": "_PSE_",
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "financialEntity": 16,
  "accountType": 1,
  "settings": {
      "entityCode": "170892",
      "serviceCode": "15916855-8"
      "isEcommerce": true
  },
  "threeDS": false
}
```
<!--
type: tab
title: ATH(Efectivo) Colombia
-->
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
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |


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

<!--
type: tab
title: Botón Bancolombia
-->

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


<!--
type: tab
title: Credibanco
-->

# Credibanco

- Visa (CR_VS)
- AMEX (CR_AMEX)
- Diners (CR_DN)

Configuración general de los medios de pago

Para credibanco hay 2 alternativas, si tenemos un certificado de credibanco podemos proporcionar el id y de no existir el certificado de credibanco debemos proporcionar la información requerida para crearlo


Caso con certificado creado

| Field Name| Required  | Description | Example | Observations |
 ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  |
| code | YES | Propiedad de la request de la api que determina el medio de pago | CR_VS |
| order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| comissionValue | NO |  | 2.5 |  |
| accountNumber | NO | | 26546 |  |
| accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| pfxID | YES |	Identificador del certificado de credibanco exitente, este atributo se envía dentro del objeto "settings" | 12
| isEcommerce | YES| Propiedad de la request de la api que determina si es un comercio electrónico| true| |
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

---------------------------------------------------

**Caso sin certificado existente**



| Field Name | Required  | Description | Example | Observations |
| ----------- | --------- | ----------- | ------- | ------------ |
| financialEntity | YES |  | 16 |  |
| code | YES | Propiedad de la request de la api que determina el medio de pago | CR_VS |
| order | NO | | 2 | Indica la prioridad que se tiene en caso de que exita la misma franquicia pero de diferentes redes procesadoras, es decir, si se tiene AMEX de redeban y credibanco, la que tenga la priodidad 1 es la que va a intentar procesar primero la transacción. |
| comissionModel | NO |  | F | Sus valores posibles son F y P , donde F representa Valor Fijo y P representa  Valor en Porcentaje |
| comissionValue | NO |  | 2.5 |  |
| accountNumber | NO | | 26546 |  |
| accountType | NO | | 2 | Sus valores posibles son 1, 2 y 3, donde  1 representa SAVINGS(Ahorros), 2 representa  CURRENT(Corriente), y 3 representa CREDIT CARD(Tarjeta de crédito) |
| username | YES| usuario de la terminal| userxx| |
| password | YES| contraseña de la terminal| passwordxx| |
| retailCode | YES |  | 011211407 | Código único de venta no presente en la request este atributo se envía dentro del objeto "settings" | 
| terminalNumber | YES |	Terminal en la que procesa el comercio en la red | 1234568 | En la request, este atributo se envía dentro del objeto "settings" |
| isEcommerce | YES| Propiedad de la request de la api que determina si es un comercio electrónico| true| |
| threeDS | YES| Propiedad de la request de la api que determina si un medio de pago requiere ThreeDS| true| |

---------------------------------------------------

## Información por paises:

**Colombia**

Métodos de pago:

- Visa (CR_VS)
- AMEX (CR_AMEX)
- Diners (CR_DN)

Observaciones:

- Se debe configurar el certificado
- Si permite threeDS
- No se usan reglas de crédito

Ejemplo de objeto paymentMethod con certificado **no** existente:

```json
{
  "code": "CR_VS",
  "order": 3,
  "financialEntity": 16,
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "accountType": 1,
  "settings": {
      "username": "FIDUCOLDEX02",
      "password": "FIDUCOLDEX02",
      "retailCode": "011211407",
      "terminalNumber": "1234568",
      "isEcommerce": true
  },
  "threeDS": true
}
```

Ejemplo de objeto paymentMethod con certificado existente:

```json
{
  "code": "CR_VS",
  "order": 3,
  "financialEntity": 16,
  "commissionModel": "F",
  "commissionValue": 0,
  "accountNumber": "1234567811",
  "accountType": 1,
  "settings": {
      "pfxID": 342,
      "isEcommerce": true
  },
  "threeDS": true
}
```

---------------------------------------------------


<!--
type: tab
title: Métricas de los comercios
-->

# Métricas de los comercios

En el índice de comercios, en la parte lateral derecha, se encuentra el acceso a la funcionalidad de métricas para los comercios, para acceder a esta, haga clic en el botón **Métricas**.

![](https://wiki.placetopay.com/images/2/20/Metric-options.png)

### Detalle de la métrica:

Al hacer clic en el botón **Métricas**, se redireccionará a la siguiente vista con el detalle de las métricas creadas, en caso de existir. Visualizará una pantalla como la siguiente:

![](https://wiki.placetopay.com/images/9/9c/Metric-detail-mpi.png)

En este detalle se evidencia las métricas creadas para diversos comercios.

## Crear nueva métrica:

Para crear nuevos importes puede hacerlo mediante el botón **Metricas** ubicado en el índice de comercios, y cuando no existan métricas creadas, se redireccionará a una vista como la siguiente. Haga clic en el botón **Crear**.

![](https://wiki.placetopay.com/images/5/53/Create-merchant-1.png)

También, puede crear nuevas métricas, yendo al índice de métricas y haciendo clic en el botón **Generar nueva métrica**.

Visualizará el siguiente formulario de creación de métrica seleccionando cualquiera de las rutas de creación ya mencionadas:

![](https://wiki.placetopay.com/images/e/ee/Metric-form-create-merchant.png)

Diligencie teniendo en cuenta la siguiente información:

- **Nombre:** Ingrese en este campo el nombre con el cual desea nombrar la métrica conforme a la función que va a tener.

- **Comercios:** Seleccione de la lista uno o varios comercios para los cuales desea generar la métrica.

- **Rango de fecha:** Seleccione del calendario una fecha inicial y una final para crear un rango y obtener a partir de este los datos, luego dé clic en el botón de check.

<!--
type: tab
title: Información detallada
-->

# Información detallada del comercio

Para ir a los detalles de un comercio, haga clic en la acción **Ver** del menú desplegable del comercio. 

En la vista del detalle se encuentra la información con la cual se creó el comercio, el estado en que se encuentra(está habilitado o no), las fechas de creación del comercio y de actualización y los usuarios que hicieron la creación y/o la actualización.

Además, en la parte lateral derecha, hay un botón para acceder al formulario de edición en caso de requerirlo. Y a la opción de eliminar.

Además, tiene los accesos para gestionar las sucursales de un comercio, los contactos y los adjuntos.

En la siguiente imagen se resalta el acceso a cada uno de estos módulos y se describen a continuación:

![](https://wiki.placetopay.com/images/4/49/Merchant-components.png)

<!--
type: tab
title: Gestión de sucursales 
-->

# Gestión de sursales

Para acceder a este menú, haga clic en el menú **Sucursales**, que se ubica al lado derecho del menú **Detalles del comercio**, en el detalle del comercio.

Luego visualizará una vista similar a la siguiente:

![](https://wiki.placetopay.com/images/f/fb/Merchant-branches.png)

En ella encontrará el listado de sucursales agregadas para el comercio, un buscador de sucursales en el cual puede hacer búsquedas por nombre, marca o país. Además, de las acciones y el botón para crear nueva sucursal.

### Agregar una nueva sucursal:

Para crear una nueva sucursal para el comercio, haga clic en el botón **Crear**, ubicado en la parte lateral derecha y visualizará un formulario como el siguiente:

![](https://wiki.placetopay.com/images/5/5d/Create-branch.png)

Para diligenciarlo tenga en cuenta los siguientes datos:

- **Nombre:** Ingrese en este campo el nombre de la sucursal que va a crear.

- **Marca:** Ingrese en este campo el nombre de la marca oficial del comercio al cual le va a crear una nueva sucursal.

- **País:** Seleccione de la lista desplegable el país dónde opera la sucursal.

- **Moneda:** Seleccione de la lista desplegable la moneda con la cual procesa las transacciones la sucursal.

- **Url:** Ingrese una URL válida que funcionará para conectar la sucursal con MPI. A esta URL se redirigirá el usuario al procesar una autenticación.

- **Habilitar/Deshabilitar:** Puede habilitar o deshabilitar la sucursal, deslizando el botón tipo switch con nombre *Habilitar* cuando está deshabilitada la sucursal, o con nombre *Deshabilitar* cuando está habilitada y desea deshabilitarla.

<!--
type: tab
title: Gestión de contactos 
-->

# Gestión de contactos

Para acceder a este menú, haga clic en el menú **Contactos**, que se ubica al lado derecho del menú **Sucursales**. 

Luego visualizará un índice como el siguiente:

![](https://wiki.placetopay.com/images/3/3d/Contacts-index.png)

En ella encontrará el listado de contactos agregados para el comercio, un buscador de contactos en el cual puede hacer búsquedas por nombre, tipo o correco electrónico. Además, de las acciones y el botón para crear un nuevo contacto.

### Agregar un nuevo contacto:

Para crear una nueva sucursal para el comercio, haga clic en el botón **Crear**, ubicado en la parte lateral derecha y visualizará un formulario como el siguiente:

![](https://wiki.placetopay.com/images/c/c1/Create-contact.png)

Para diligenciarlo tenga en cuenta los siguientes datos:

- **Tipo de adjunto:** Seleccione de la lista desplegable el tipo de contacto que desea agregar al comercio.

- **Nombre:** Ingrese el nombre del contacto o persona.

- **Apellido:** Ingrese el apellido del contacto o persona.

- **Correo electrónico:** Ingrese el correo electrónico
del contacto.

- **Cargo:** Ingrese el nombre del cargo que ocupa el contacto.

- **Tipo de documento:** Seleccione de la lista desplegable el documento con el cual se identifica el contacto.

- **Documento:** Digite el número de documento correspondiente al tipo seleccionado.

- **Móvil:** Ingrese el teléfono correspondiente al móvil, ingrese solo números en este campo.

- **Teléfono:** Ingrese el teléfono correspondiente al fijo u otro número móvil, ingrese solo números en este campo.

- **Dirección:** Ingrese la direcció en la cual se encuentra ubicado el contacto.

<!--
type: tab
title: Gestión de adjuntos 
-->

# Gestión de adjuntos

Para acceder a este menú, haga clic en el menú **Adjuntos**, que se ubica al lado derecho del menú **Contactos**. 

Luego visualizará un índice como el siguiente:

![](https://wiki.placetopay.com/images/d/d3/Attachments-index.png)

En ella encontrará el listado de adjuntos agregados para el comercio, un buscador de adjuntos en el cual puede hacer búsquedas por nombre o tipo. Además, de las acciones y el botón para crear un nuevo adjuntos.

### Agregar un nuevo adjunto:

Para crear una nueva sucursal para el comercio, haga clic en el botón **Crear**, ubicado en la parte lateral derecha y visualizará un formulario como el siguiente:

![](https://wiki.placetopay.com/images/1/15/Attachment-create-mpi.png)

Para diligenciarlo tenga en cuenta los siguientes datos:

- **Tipo de adjunto:** Seleccione de la lista desplegable el tipo de archivo adjunto que desea cargar.

- **Nombre:** Ingrese en el campo el nombre a asignarle al nuevo tipo de archivo adjunto.

- **Carga de archivo:** Haga clic en el campo y se redireccionará a los archivos de su equipo personal, seleccione y cargue el archivo que desea subir.

### ¿Cómo descargar el archivo creado?

Al dar clic en el botón **Guardar**, se redireccionará a una vista como la siguiente, en la cual puede descargar el archivo creado, haciendo clic en el botón **Descargar**:

  ![](https://wiki.placetopay.com/images/a/a7/Attachment-detail.png)

<!--
type: tab
title: Otras gestiones 
-->

# Otras gestiones en el detalle del comercio

En el detalle de un comercio se encuentra la gestión de diversos componentes y configuraciones que requiere este para su buen funcionamiento.

La siguiente imagen muestra cada una de estas secciones y se procede a describir cada una a continuación:

![](https://wiki.placetopay.com/images/2/21/Merchant-detail-sections.png)

## Sección de métricas

En esta sección se muestran las métricas para el comercio seleccionado. Existen dos tipos de métricas actualmente:

### Métrica de total de transacciones procesadas

Esta métrica muestra en una gráfica, la cantidad de transacciones realizadas, diferenciadas por estados.

### Métrica de montos de transacciones procesadas

Esta métrica muestra en una gráfica, el monto de las transacciones realizadas en MPI y diferenciadas por estados.

## Sección de tokens

En esta sección se listan todos los tokens de acceso creados para el comercio específico, estos se encuentran listados en una tabla con el nombre, el usuario que lo creó, la fecha de creación y expiración y las acciones que en este caso solo tiene disponible la acción de eliminar y crear nuevo token.

### ¿Cómo crear un nuevo token?

Para crear un nuevo token para un comercio, que le permite el acceso para procesar una autenticación con la aplicación de MPI, deberá hacer clic en el botón **Crear token**.

Se mostrará un formulario como el siguiente, donde únicamente le pedirá ingresar un nombre para identificar al nuevo token a crear:

![](https://wiki.placetopay.com/images/e/e2/Form-toke-create.png)

Luego de dar clic en el botón **Crear**, se redireccionará al detalle del token creado y se visualizará como el siguiente:

![](https://wiki.placetopay.com/images/e/e1/Token-detail.png)

> Copie el bloque de texto correspondiente al token y consérvelo ya que este no se podrá visualizar de nuevo y si lo pierde, deberá crear un nuevo token.


## Sección de adquirientes suscritos

En esta sección se listan todos los adquirientes suscritos al comercio específico, estos se encuentran listados en una tabla con la franquicia, la versión del protocolo, el adquiriente, el código identificador, el estado del certificado SSL, el estado de la suscripción del adquiriente y las acciones que tiene disponible la suscripción.

### ¿Cómo crear una nueva suscripción?

Para crear una nueva suscripción para un comercio, deberá hacer clic en el botón **Suscribir adquiriente**.

Se mostrará un formulario como el siguiente:

![](https://wiki.placetopay.com/images/d/df/Suscription-create.png)

### Funcionalidades para las suscripciones:

Al final de cada registro de suscripción, se encuentra un menú con tres puntos, haga clic en este y se desplegarán las acciones disponibles, las cuales son:

- **Editar:** Puede editar la información con la cual se creó la suscripción, haciendo clic en la opción *Editar*. 

- **Eliminar:** Puede eliminar la suscripción, haciendo clic en la opción *Eliminar*. 

### ¿Cómo validar una suscripción?

Para probar la validez de una suscripción de adquiriente para un comercio, diríjase al final del registro de la suscripción y haga clic en el botón con ícono de probeta, como lo indica la siguiente imagen:

![](https://wiki.placetopay.com/images/4/42/Validate-suscription.png)

Luego se desplegará una ventana donde le indicará el estado de validación de la suscripción, se visualizará similar al siguiente ejemplo para una validación de suscripción exitosa:

![](https://wiki.placetopay.com/images/3/30/Success-subs.png)

Y el siguiente ejemplo para una validación fallida:

![](https://wiki.placetopay.com/images/2/20/Fail-subs.png)

> Si la validación de la suscripción resulta fallida, debe revisar nuevamente que su certificado SSL esté firmado correctamente, que no esté expirado, que la franquicia y el adquiriente estén habilitados, y los rangos de tarjeta correctos y cargados.

<!-- type: tab-end -->