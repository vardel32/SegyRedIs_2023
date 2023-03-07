# Bandit Level 19 → Level 20
#Bandit #OverTheWire 
## Objetivo
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.
## Solución
El setuid que se nos da en el directorio actual nos da los permisos del usuario bandit20, ejecutando este setuid se puede obtener la contraseña para el usuario bandit20. La contraseña se encuentra dentro del directorio que contiene las contraseñas de todos los usuarios.

```bash
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ file bandit20-do
bandit20-do: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=c148b21f7eb7e816998f07490c8007567e51953f, for GNU/Linux 3.2.0, not stripped
bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

===VxCazJaVykI6W36BkBU0mJTCM8rR95XT==
## Notas adicionales
setuid (set user identity) setgid (set group identitiy) son configuraciones que permiten a usuarios correr ejecutables con los permisos de sistema que poseen ya sea el usuario dueño de ese ejecutable o el grupo dueño de ese ejecutable.
Habitualmente otorgan permisos superiores o en su defecto, permisos especificos.

## Referencias
- setuid/setgid https://en.wikipedia.org/wiki/Setuid