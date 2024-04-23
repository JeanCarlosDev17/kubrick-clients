---
stoplight-id: of1vsv1m1hlss
tags: [reasonCodes]
---

# ReasonCodes

| Name                     | Code | Description                                                                                                                                                                                          |
| ------------------------ | ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BAD_REQUEST              | BR   | La request no pudo ser realizada, la informacion enviada es erronea.                                                                                                                                 |
| FAILED_AUTHENTICATION    | FA   | Error en la autenticación o credenciales inválidas.                                                                                                                                                  |
| FAILED_THREE_DS_CREATION | FTC  | La request no se ha completado por que ha ocurrido un error al momento de crear un recurso de ThreeDS                                                                                                |
| REQUEST_COMPLETED        | RC   | La request se completó con éxito.                                                                                                         |
| REQUEST_PARTIAL          | RPA  | La request fue procesada, sin embargo, uno o mas recursos solicitados no fueron creados correctamente, esto puede darse por error en la comunicación con el servicio de Rest, threeDS o Micrositios. |
| REQUEST_FAILED           | RF   | La request fue procesada pero fallo                                                                                                                                                                  |
| REQUEST_PENDING          | RPE  | La petición solictada esta pendiente de ser procesada                                                                                                                                                |
| RESOURCE_STORED          | RS   | La request fue procesada y creados y almacenado la información de los recursos solicitados                                                                                                           |
| RESOURCE_NOT_FOUND       | RNF  | La request no puede ser resuelta el recurso solictado no existe                                                                                                                                      |
| RESOURCE_UPDATED         | RU   | La request fue procesada y la infomación del recurso solicitado fue actulizada                                                                                                                       |
| UNAUTHORIZED             | UA   | La request no puede ser procesada no tiene permiso para acceder al recurso solicitado                                                                                                                |
