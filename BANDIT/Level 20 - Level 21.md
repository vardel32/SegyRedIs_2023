# Titulo
#Bandit #OverTheWire 
## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think
## Solución

Se utiliza el comando `nc` con los parametros `-lnvp` y se le da como entrada la contraseña del nivel actual. Se proporciona el `&` para liberar la terminal y poder ejecutar el siguiente comando.
Lo que hace este comando es dejar escuchando el puerto 2023. Tras dejar escuchando netcat en el puerto 2023 se ejecuta el setuid `suconnect` para recibir la contraseña del siguiente nivel.

```bash
bandit20@bandit:~$ nc -lnvp 2023 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[2] 3062497
[1]   Exit 1                  nc -lnvp 666 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ Listening on 0.0.0.0 2023
^C
bandit20@bandit:~$ ./suconnect 2023
Connection received on 127.0.0.1 33836
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[2]+  Done                    nc -lnvp 2023 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ exit

```

===NvEJF7oVjkddltPSrdKEFOllh9V1IBcq===
## Notas adicionales
- l - parametro que deja el puerto en modo `listen`, es decir, escuchando
- n - parametro que evita direciones DNS, utiliza solo direcciones IP numericas
- v - parametro para `verbose` dar información sobre el comando ejecutado
- p - parametro que indica el puerto utilizado.
## Referencias
- https://phoenixnap.com/kb/nc-command