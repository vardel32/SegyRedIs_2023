# Bandit Level 11 → Level 12
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Solución
En este reto nos encontramos con un archivo de texto que contiene la bandera cifrada en rot13.

```bash
bandit11@bandit:~$ file data.txt
data.txt: ASCII text
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ 
```

Utilizando cyberchef podemos rotar las letras 13 posiciones para obtener la bandera.
The password is 
===JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv===

## Notas adicionales

## Referencias
Cyberchef
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=R3VyIGNuZmZqYmVxIHZmIFdJQU9PU0Z6TWpYWEJDMEtvU0tCYko4cHVRbTVsSUVp