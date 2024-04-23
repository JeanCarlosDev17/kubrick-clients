---
stoplight-id: qdp6e163d99rb
tags: [autenticación]
---

# Autenticación

La autenticación es por medio de un bearer token enviado en el header “Authorization”, el token es generado por los administradores de la API. A continuación se mostrarán los headers recomendados:

| Name          | Required | Description                       |
| ------------- | -------- | --------------------------------- |
| Authorization | YES      | Bearer eYjdsjwpdm92j3k2j313j2m... |
| Content-type  | YES      | application/json                  |
| Accept        | YES      | application/json                  |

Se recomienda que el token no esté expuesto en el código, se debe recuperar desde un archivo de variables de entorno o en caso de almacenarse en la base de datos debe estar encriptado.
