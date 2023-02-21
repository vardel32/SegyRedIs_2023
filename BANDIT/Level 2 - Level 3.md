# Bandit Level 2 → Level 3
#OverTheWire #Bandit 
## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory
## Solución
Nos encontramos con un archivo que contiene espacios el su nombre, naturalmente al tratar de abrir el archivo lanzara un error pues marcar los espacios dentro del comando tomaria como que cada palabra es un archivo o comando distinto que el bash no conoce.
Esto se puede evitar colocando el nombre del archivo entre comillas.

``` bash
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ file "spaces in this filename"
spaces in this filename: ASCII text
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

```

Acceso para el siguiente nivel:
==aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG==
## Notas adicionales

## Referencias