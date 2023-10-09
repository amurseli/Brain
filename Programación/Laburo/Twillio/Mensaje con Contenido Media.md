---
tags:
  - Tutoriales
---

Leer [Aquí](https://www.twilio.com/docs/content/create-templates-with-the-content-editor).

Para poder usar una url a un contenido media uqe llegue por parámetro (como sería un pdf que cambia dependiendo a quien se lo mandes) se utiliza el [[Content Editor]]. Aí, se pueden crear diferente templates, similar a como se hacía para los mensajes regulares. En el caso del content editor, también es necesario proveer a [[Twillio]] de ejemplos de cada uno de los parámetros.

Después de la verificación de whatsapp, el template tendrá asociado un Content ID, el cual se ingresa como parámetro en la funcion `Client.messages`, junto con un diccionario especificando cada uno de los parámetros.

Es necesario enviar el mensaje desde un [[Messaging Services|Messaging Service]], ya que es necesario un Sid del tipo MGXXXXX.

```js
 const mensaje = await client.messages
            .create({
              contentSid: contentSid, //Template ID
              messagingServiceSid: process.env.MS_SID,
              contentVariables: JSON.stringify({
                1: args.body.razonsocial,
                2: args.body.importetotal,
                3: pago,
                4: getPathAfterBaseUrl(mediaUrl, baseUrl)
              }),
              to: to
             })
```

