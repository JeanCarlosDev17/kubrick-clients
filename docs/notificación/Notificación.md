---
stoplight-id: dh665oupvggs9
tags: [notificación]
---

# Notificación

Al momento de finalizar el procesamiento de una petición, sin importar que esta sea exitosa, fallida o parcial, se notificará a la url “statusWebhook” indicada en la petición con la información de los recursos solicitados, para el caso de la integración [create-from-merchant](reference/Kubrick.json/paths/\~1api\~1integration\~1create-from-merchant/post), se enviará una notificación 

Esta URL debe estar expuesta en un puerto público (80 o 443) y debe tener la capacidad de recibir una petición tipo POST.

Para ver la estructura completa de la notificación [observe el modelo de notification](reference/Kubrick.json/components/schemas/notification).

# Proceso de sonda

Si bien el servicio de notificación asegura el envío de la misma una vez se hayan procesado las peticiones, recomendamos que se implemente un proceso de sonda, el cual, consiste en un cronjob que consulta al endpoint de [get-information](reference/Kubrick.json/paths/\~1api\~1integration\~1get-information\~1{integrationId}/post), esto con el fin de tener un sistema de contingencia a la notificación.
