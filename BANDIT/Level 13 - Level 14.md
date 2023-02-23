# Bandit Level 13 → Level 14
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on
## Solución
Dentro de este nivel no se nos da la contraseña de usuario para el siguiente nivel, pero sí se nos da una una llave SSH privada. Mediante esta llave privada se puede acceder al usuario bandit 14 y desde la carpeta en la cual se almacenan las contraseñas se puede extraer la clave.

```bash
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
...
...
...
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```

===fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq===

## Notas adicionales
Utilizando el comando ssh -i se puede dar como parametro la llave privada para evitar que se pida la contraseña.
## Referencias