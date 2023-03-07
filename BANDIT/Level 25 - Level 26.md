# Bandit Level 25 → Level 26
#Bandit #OverTheWire 
## Objetivo
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.
## Solución
Se corrobora que el usuario bandit26 contiene un 

```bash
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
bandit25@bandit:~$ 
bandit25@bandit:~$ ls
bandit26.sshkey


```

Utilizar la llave ssh dada muestra un archivo y después cierra la sesión.
Se tiene que hacer muy pequeña la pantalla para que el comando More no puedea ejecutarse bien, se teclea "v" y se entra en modo editor de vim
escape, :e /etc/bandit_pass/bandit26 

===c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1===
## Notas adicionales
El comando more muestra un archivo muy grande en varias pantallas, si no cabe en una sola.
## Referencias