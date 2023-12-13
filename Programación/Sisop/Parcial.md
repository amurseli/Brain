	¿Que es un deadlock? Describa por lo menos tres casos diferentes en el que puede suceder en esta situación.

Un deadlock es un error en el manejo de threads, ocurre cuando no se tienen los recursos suficientes para avanzar con un hilo, ni los va a conseguir, generalmente porque otro hilo los esta usando y no va a soltarlos. Para que ocurra un deadlock, hay cuatro situaciones que deben ocurrir simultáneamente.

- **Exclusión Mutua**: Los hilos reclaman el acceso absoluto y exclusivo a un recurso.
- **Hold-And-Wait**: El thread que tiene dicho recurso, lo va a mantener hasta que cierta condición se cumpla
- **No Preemtion**: Los threads no son preemptivos, por lo que no se puede frenar su ejecución a la fuerza.
- **Circular Wait**: Un circulo cerrado de dependencias. El hilo 1 espera un recurso que solo tiene el hilo 2, el dos uno q solo tiene el 3, y el hilo n uno que solo tiene el hilo 1.

*Caso 1:* Suponiendo que dos hilos, 1 y 2, requieron los recursos a y b, simultánemante para funcionar. Si 1 agarra el a y 2 el b, ambos quedarán esperando el recurso restante, y se producirá un deadlock.
*Caso 2:* Por lo que sea, el hilo 1 llega siempre a los recursos a y b, terminando, pero otro hilo llega antes de que 2 llegue, haciendo que 2 caiga en starvation.
*Caso 3:* El hilo 1 siempre tiene los recursos antes que el 2, por lo que el 2 cae devuelta en starvation.

	Explique la idea de MLFQ y porque es mejor que otras porlíticas de Scheduling

MLFQ es una política de scheduling que se centra en el uso de múltiples colas con diferentes sub-políticas y prioridades. Intenta optimizar el turnaround time y el response time.

Si dos tareas tienen la misma prioridad, se suele usar un Round Robin para decidir entre ellas, y en caso de ser corridas, se les baja la prioridad. Entonces:
- Si A tiene mayor prioridad que B, A se ejecuta, si tienen la misma prioridad, se ejecuta Round Robin
- Si un programa entra a MLFQ, siempre entra con la prioridad más alta
- Si una tarea no termina una vez acabado su time slice, su prioridad se reduce, no importa si decide soltarlo antes de tiempo. (para impedir el gaming)

El mayor problema de este approach, es que si muchas tareas cortas entran al sistema sin parar, una tarea largam, con su prioridad reducida, nunca se va a terminar. A esto se le llama caer en Starvation. Para solucionarlo, se introduce un sistema de Boosts, que cada un tiempo determinado, reinician la prioridad de todos los procesos, a la prioridad más alta, así que por pura probabilidad, tarde o temprano, la tarea larga se va a ejecutar.

	Explique como se resuelven las traducciones a memoria físico en un modelo con tlb

