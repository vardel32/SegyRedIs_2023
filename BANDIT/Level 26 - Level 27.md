# Bandit Level 26 → Level 27
#Bandit #OverTheWire 
## Objetivo
Good job getting a shell! Now hurry and grab the password for bandit27!
## Solución
Es el mismo escenario, es requerido minimizar la pantalla para hacer fallar al comando more. Sin embargo en esta ocasión no se puede leer el archivo de la contraseña de bandit 27.
Se teclea la letra v, entramos en el editor y se ejecuta la linea de comando, es decir se consigue un bash desde el editor.

```bash
  _                     _ _ _   ___   __
 | |                   | (_) | |__ \ / /  
 | |__   __ _ _ __   __| |_| |_   ) / /_  
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \
 | |_) | (_| | | | | (_| | | |_ / /| (_) |
:shell
bandit26@bandit:~$ ls
bandit27-do  text.txt

bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
bandit26@bandit:~$ 


```

===YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS===

## Notas adicionales

## Referencias