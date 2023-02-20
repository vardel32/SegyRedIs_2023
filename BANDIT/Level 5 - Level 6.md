# Bandit Level 5 → Level 6
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:
-   human-readable
-   1033 bytes in size
-   not executable
## Solución
Se utiliza el comando `find` con los parametros del tipo de archivo y el tamaño para encontrarlo.

```bash
bandit5@bandit:~$ find -type f -size 1033c
./inhere/maybehere07/.file2
bandit5@bandit:~$ cat ./inhere/maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Notas adicionales

## Referencias
Comando find linux: 
https://www.ionos.mx/digitalguide/servidores/configuracion/comando-linux-find/#:~:text=Para%20encontrar%20un%20archivo%20en,todas%20las%20distribuciones%20de%20Linux.