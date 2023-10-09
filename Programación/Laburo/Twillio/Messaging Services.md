Los Messaging Services son una herramienta de organización para manejar mejor a los [[Whatsapp Sender|Senders]], y sus distintas características y configuraciones.

Los Messaging Services ofrecen servicios como [[Link Shortening en Twilio]] y permite administrar tus diferentes Senders en un solo lugar.

En el código, el Sid reemplaza el numero en el parámetro "To"

```js
 const mensaje = await client.messages
            .create({
              contentSid: contentSid, 
              messagingServiceSid: process.env.MS_SID, //Aquí va el ID del servicio
              contentVariables: JSON.stringify({
                1: args.body.razonsocial,
                2: args.body.importetotal,
                3: pago,
                4: getPathAfterBaseUrl(mediaUrl, baseUrl)
              }),
              to: to
             })
```