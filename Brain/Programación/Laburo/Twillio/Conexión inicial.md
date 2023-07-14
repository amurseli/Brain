Para poder conectarse correctamente con [[Twillio|twilio]], con una cuenta no upgradeada, solo hace falta entrar a [la consola](https://console.twilio.com/). Desde ahí, iniciamos un Whatsapp sandbox (siguiendo los pasos de la página)

Desde un script the [[Javascript]], usamos este código.

```js
const accountSid = SID; #Protegido por una env variable
const authToken = TOKEN;
const client = require('twilio')(accountSid, authToken);

client.messages

.create({
    body: 'Your appointment is coming up on July 21 at 3PM',
    from: 'whatsapp:+14155238886', #Numero de Twillio
    to: 'whatsapp:+numero', #Tu Numero

})

.then(message => console.log(message.sid));
```

Al correr esto, se va a iniciar una conversación directa con twilio.

Pasar un media (PDF o Video)

```js
const accountSid = SID; #Protegido por una env variable
const authToken = TOKEN;
const client = require('twilio')(accountSid, authToken);

client.messages

.create({
    body: 'Your appointment is coming up on July 21 at 3PM',
    from: 'whatsapp:+14155238886', #Numero de Twillio
    to: 'whatsapp:+numero', #Tu Numero
    mediaUrl: '' #Algun media en caso de querer pasar media.

})

.then(message => console.log(message.sid));
```

Para iniciar sesión con la empresa, sigo con [[Inicio de sesión Guiado]]. 