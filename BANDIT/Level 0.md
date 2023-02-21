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
## Notas adicionales
La conexión mediante SSH se realiza con los siguientes parametros.
- Comando SSH.
- Usuario
- IP
- Puerto (opcional mediante el parametro `-p`)
SSH (Secure SHell, interprete de órdenes seguro) es el nombre de un protocolo y del programa que lo implementa cuya principal funcion es el acceso remoto a un servidor por medio de un canal seguro en el que toda la información está cifrada.
## Referencias
https://www.wikihow.com/Use-SSH
https://en.wikipedia.org/wiki/Secure_Shell