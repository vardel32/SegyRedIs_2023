# Bandit Level 17 → Level 18
#Bandit #OverTheWire 
## Objetivo
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**
## Solución
Se utiliza el comando `diff` para comparar las diferencias entre el contenido de ambos archivos.

```bash
bandit17@bandit:~$ ls
passwords.new  passwords.old
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< f9wS9ZUDvZoo3PooHgYuuWdawDFvGld2
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

===hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg===

## Notas adicionales

## Referencias
- Uso del comando `diff` https://geekland.eu/comparar-directorios-y-archivos-comando-diff-linux/