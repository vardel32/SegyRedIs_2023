# Bandit Level 6 → Level 7
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

-   owned by user bandit7
-   owned by group bandit6
-   33 bytes in size
## Solución
Para solucionar este reto una vez más se utliza el comando `find` con los parametros de tipo de archivo, tamaño, usuario propietario y el grupo propietario.
Nos arroja una amplia lista de archivos que cumplen con estas caracteristicas, sin embargo hay solo uno al cual podemos acceder, dicho archivo nos proporciona la clave.

```bash
bandit6@bandit:/$ find -type f -size 33c -user bandit7 -group bandit6
find: ‘./var/lib/dpkg/info/bandit7.password
bandit6@bandit:/$ cat ./var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

===z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S===
## Notas adicionales

## Referencias