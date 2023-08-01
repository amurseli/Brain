Como infraestructura, decidimos utilizar AWS Lambda. Utilizando las Layers para importar las bibliotecas de Twilio y tuvimos que conectar la VPC para que pueda agarrar internet. También es importante notar que hubo un error con el controlador handler, que puede verse en la sección “Confguración del tiempo de ejecución”

Usando el código de [[Conexión inicial]], y setenado las env variables, pudimos hacerlo funcionar.

[El Lambda](https://sa-east-1.console.aws.amazon.com/lambda/home?region=sa-east-1#/functions/mensajes-twilio-whatsapp?tab=code) en el que esta cargado todo el código.

