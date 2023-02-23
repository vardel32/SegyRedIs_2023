# Bandit Level 9 → Level 10
#OverTheWire #Bandit 
## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
## Solución
Para la solucion de este reto se utiliza el comando cat seguido del comando strings, que permite mostrar de forma legible los datos contenidos dentro del archivo.

```bash
bandit9@bandit:~$ cat data.txt | strings 
n.E========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

```

===G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s===
## Notas adicionales

## Referencias