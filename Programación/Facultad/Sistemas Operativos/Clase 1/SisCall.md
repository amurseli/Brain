---
tags: Sisop
---
Es una API para hablar con el núcleo, el Bare Metal.

### fork()
```C
#include <unistd.h>
pid_t fork(void);
```

Crea unacopia exacta de el proceso que recibe por parametro, exceptuando por el pid. Uno de estos dos procesos será el padre (el original) y otro será el hijo (el nuevo). 

```C
int pid = fork();
if(pid == 0){
	printf("child: exiting\n");
} else if (pid > 0){
	printf("parent: child=%d\n", pid);
} else {
	prinf("fork error\n");
}
```

Es la única siscall que retorna dos valores, uno al padre y uno al hijo, el hijo va a recibir un 0, mientras que el padre recibirá el pid del hijo.

### wait()

Se utiliza para esperar un cambio de estado en el proceso hijo. Es decir, espera a que su hijo terminde de hacer lo que tiene que hacer, muera y luego puede seguir.

```C
#include <sys/wait.h>
pid_t wait(int *_Nullable wstatus);
```

### exit()

Como su nombre indica, cierra un proceso, su parámetro es el código de salido, por qué se cerró.


### execve()

```c
#include <unistd.h>
int execve(const char *pathname, char*const_Nullable argv[],char *cosnt_Nullable envp[])
```

Reemplaza todo el contenido de un proceso, su heap, stack, code, data, etc y pasa a correr otra cosa. Es la forma de modificar un proceso para que haga lo que uno quiere.
Así es comom funcionan las consolas, se tiene un archivo, se le hace un fork y se le hace un execve para reemplazarla por el código deseado


### dup()

Duplica un [[File Descriptors|file descriptor]] y lo coloca en el primer lugar libre de la tabla de file descriptors.

### pipe()

Un pipe es un pequeño **buffer en el kernel**, expuesto a los procesos como dos file descriptors, al escribir en uno de los extremos, este contenido esta disponible en el otro lado. Es un vector de dos enteros, ``[1] ``para la escritura y ``[0]`` para la lectura.

















