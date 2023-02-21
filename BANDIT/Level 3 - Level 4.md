# Bandit Level 3 → Level 4
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.
## Solución
Dentro de este reto nos encontramos con un archivo de texto oculto con un punto (.) antepuesto. Es decir, este archivo no se puede observar mediante el comando habitual `ls`, para poder observar este tipo de archivos se le deben de dar los parametros `-la` al comando mencionado.

```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Jan 11 19:19 .
drwxr-xr-x 3 root    root    4096 Jan 11 19:19 ..
-rw-r----- 1 bandit4 bandit3   33 Jan 11 19:19 .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

```

Acceso para el siguiente nivel
==2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe==
## Notas adicionales

## Referencias