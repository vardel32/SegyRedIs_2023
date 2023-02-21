# Bandit Level 8 → Level 9
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once.
## Solución
Para la solución de este reto se emplean tres comandos distintos dirigidos mediante pipelines `|` .
El primero a utilizar es `cat`, se utiliza para la lectura del archivo, esta lectura es redirigida al siguiente comando `sort` utilizado para colocar de forma adyacente todas las lineas iguales. El texto ordenado es redirigido al comando `uniq -u` el cuál cumple la funcion de mostrar solo las lineas únicas (que no se repiten).

```bash
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

## Notas adicionales

## Referencias
https://www.ibm.com/docs/en/aix/7.2?topic=u-uniq-command