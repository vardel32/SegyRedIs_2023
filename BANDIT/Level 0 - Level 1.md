# # Bandit Level 0 → Level 1
#OverTheWire #Bandit 
## Objetivo
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Solución
```bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ file readme
readme: ASCII text
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

```

Obtenemos la contraseña para el siguiente nivel.

==NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL==

## Notas adicionales

## Referencias