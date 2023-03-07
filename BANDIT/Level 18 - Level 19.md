# Bandit Level 18 → Level 19
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.
## Solución
Se otorga un parametro especial, un parametro que contiene el comando `cat`para poder realizar una lectura del archivo `readme`.

```bash
┌──(kali㉿kali)-[~]
└─$ ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

===awhqfNnAbc1naukrpqDYcF95h7HoMTrC===

## Notas adicionales
Al ejecutar el comando que permite la conexión mediante SSH, se le puede otorgar un último parametro extra, después de colocar el usuario, IP y puerto, este comando se ejecutaría inmediatamente después de loguearse.

## Referencias
https://geekland.eu/ejecutar-comandos-y-scripts-con-ssh-en-equipos-remotos/