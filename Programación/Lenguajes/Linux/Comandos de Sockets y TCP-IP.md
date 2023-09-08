---
tags:
  - TallerDeProgramacion
  - Tutoriales
  - TCP/IP
---
### [nc](https://linux.die.net/man/1/nc)

Buena pagina del man de todos los comandos para usar en [[Linux]] en relacion con tcp/ip, udp y conexiones. (Recordá usar -p en ubuntu)


### [netstat](https://linux.die.net/man/8/netstat)

Manpage a netstat, usado para ver el estado de las conexiones de toda la máquina. [ss](https://man7.org/linux/man-pages/man8/ss.8.html) tiene el mismo proósito.

- ``ss -tuplan``
- ``netstat -tauopen``

Ambos comandos muestran el estado de los puertos o conexiones activas de la máquina.

El Formato es (es una tabla doble):

| Protocol | Recv-q | Send-q    | Local Adress (puerto) | Foreign Adress | State |
| -------- | ------ | --------- | --------------------- | -------------- | ----- |
| **User** |        | **Inode** | **PID/Program name**  | **Timer**          |       |
|          |        |           |                       |                |       |


### [ifconfig](https://phoenixnap.com/kb/nc-command)

Muestra la ip de la maquina