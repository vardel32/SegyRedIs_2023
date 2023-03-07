# Bandit Level 12 → Level 13
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)
## Solución
Nos encontramos con un archivo que ha sido multiples veces comprimido, mediante pipelines se ejecuta un comando que descomprime el archivo multiples ocasiones, los formatos de compresión utilizados son ZCAT, BZCAT, TAR.

```bash
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

```

===wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw===
## Notas adicionales

## Referencias