# # Bandit Level 1 → Level 2
#OverTheWire #Bandit 
## Objetivo
The password for the next level is stored in a file called **-** located in the home directory
## Solución
```bash
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ 

```

Acceso para el siguiente nivel:
==rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi==
## Notas adicionales
El guión medio (-) dentro de Unix o Linux habitualmente es utilizado por comandos para especificar argumentos. Se pueden manejar estos archivos, se pueden crear consultar, actualizar o eliminar. Simplemente es necesario utilizar un caracter de escape, en este caso los caracteres de escape son (./).
## Referencias
- Dashed filename:. https://www.webservertalk.com/dashed-filename