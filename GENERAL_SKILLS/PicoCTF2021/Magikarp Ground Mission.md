# Magikarp Ground Mission
#picoCTF2021 #GeneralSkills 
## Objetivo
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `b60940ca`

Additional details will be available after launching your challenge instance.
## Solución
Este reto consiste en conectarnos mediante SSH a un servidor proporcionado. Se trata de una maquina Ubuntu que es capaz de ejecutar comandos de shell como `cd` y `cat`.
El reto consiste en movernos entre directorios y recolectar las partes de la bandera de este nivel.

```bash
┌──(insoportable㉿kali666)-[~]
└─$ ssh ctf-player@venus.picoctf.net -p 49741
The authenticity of host '[venus.picoctf.net]:49741 ([3.131.124.143]:49741)' can't be established.
ED25519 key fingerprint is SHA256:P1f6h95BrSVnJbm2AKhphfHHGEyAeThib/rN/AwKs24.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[venus.picoctf.net]:49741' (ED25519) to the list of known hosts.
ctf-player@venus.picoctf.net's password: 
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

...
...
...

ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  dev   instructions-to-3of3.txt  media  proc  sbin  tmp
bin	       etc   lib		       mnt    root  srv   usr
boot	       home  lib64		       opt    run   sys   var
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ~
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt 
c1754242}

```

==picoCTF{xxsh_0ut_0f_\/\/4t3r_c1754242}==

## Notas adicionales

## Referencias