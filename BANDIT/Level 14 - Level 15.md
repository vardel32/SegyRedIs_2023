# Bandit Level 14 → Level 15
#Bandit #OverTheWire 
## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
## Solución
Contraseña del nivel actual: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Se tiene que enviar la contraseña del nivel actual al puerto 30000 dentro del servidor actual.
Para esto utilizamos la herramienta netcat.

```bash
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

===jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt===
## Notas adicionales

## Referencias