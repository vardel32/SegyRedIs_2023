# Bandit Level 7 → Level 8
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**
## Solución
Para la solución de este reto se utiliza el comando grep.  Con grep en Linux puedes buscar una palabra o patrón y se imprimirá la línea o líneas que la contengan

```bash
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$ exit
```
## Notas adicionales

## Referencias
https://www.hostinger.mx/tutoriales/comando-grep-linux#:~:text=El%20comando%20grep%20perteneciente%20a,o%20líneas%20que%20la%20contengan.