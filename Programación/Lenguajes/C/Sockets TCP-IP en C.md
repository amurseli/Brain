### [Send()](https://pubs.opengroup.org/onlinepubs/000095399/functions/send.html)

Send es la funcion de C para enviar mensajes a sockets. 

```c
#include <sys/socket.h>  
  
ssize_t send(int _socket_, const void *_buffer_, size_t _length_, int _flags_);
```


### [Recv()](https://pubs.opengroup.org/onlinepubs/007904975/functions/recv.html)

Recibe un mensaje de un socket conectado.

```c
#include <sys/socket.h>  

ssize_t recv(int _socket_, void *_buffer_, size_t _length_, int _flags_);
```