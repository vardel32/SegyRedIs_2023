# Bandit 0
#OverTheWire #Bandit
## Objetivo
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is.
- **bandit.labs.overthewire.org**
- puerto 2220
- username: **bandit0**
- password: **bandit0**
## Solución
Primeramente se conecta al servidor mediante el comando SSH.
```bash
┌──(kali㉿kali)-[~]
└─$ ssh bandit0@bandit.labs.overthewire.org -p 2220

```

Posterior a eso se coloca la contraseña dada y podemos acceder para ejecutar comandos de linux.

```bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
bandit0@bandit:~$ 
```

Obtenemos la contraseña para el siguiente nivel.

==NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL==
## Notas adicionales

## Referencias
https://www.wikihow.com/Use-SSH
https://en.wikipedia.org/wiki/Secure_Shell