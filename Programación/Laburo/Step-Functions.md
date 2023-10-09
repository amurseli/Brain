Las step-Functions son un módulo nuevo de [[AWS]], que te permite encadenar la ejecucion de varios modulos diferentes, y orquestrarlos en diferentes caminos de ejecución con condicionales.

Para pasar parámteros, de un step a otro, podemos usar [[JsonPATH]] para seleccionar que partes del input del primer step pasan al segundo, y así. Estas interacciones entre parámetros, inputs y outputs puede resultar compleja, por lo que se recomienda usar el [Data flow Simulator](https://us-east-1.console.aws.amazon.com/states/home?region=us-east-1#/simulator) que AWS ofrece para simular las interacciones entre los diferentes steps.

# Flow

### [Choice](https://docs.aws.amazon.com/step-functions/latest/dg/amazon-states-language-choice-state.html)

Es utilizado, como su nombre indica, para generar una estructura de tipo if en el flujo del la función.

Pueden, dentro de este step, generarse reglas, para determinar hacia cual de los caminos seguirá la ejecución del programa.
