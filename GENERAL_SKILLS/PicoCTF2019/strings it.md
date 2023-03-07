# strings it
#picoCTF2019 #GeneralSkills 
## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?
## Solución
Primeramente creamos una carpeta para almacenar las descargas y posteriormente nos movemos ahí para descargar el archivo dado.

```bash
┌──(insoportable㉿kali666)-[~/Descargas]
└─$ mkdir -p picoCTF/generalSkills
┌──(insoportable㉿kali666)-[~/Descargas]
└─$ cd picoCTF/generalSkills 
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ wget https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
--2023-03-06 23:08:46--  https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 776032 (758K) [application/octet-stream]
Grabando a: «strings»

strings             100%[===================>] 757.84K  1.18MB/s    en 0.6s    

2023-03-06 23:08:47 (1.18 MB/s) - «strings» guardado [776032/776032]

```

Aparentemente nos encontramos con un archivo ELF, es decir un archivo ejecutble. Sin embargo al ejecutarlo nos muestra caracteres sin sentido, el propio nombre del archivo nos da una pista de por donde pordría proceder el reto.

```bash
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ . strings
/usr/bin/strings:1: no existe el fichero o el directorio: ^@^A^@^@^@\M-09^@^@^@^@^@^@@^@^@^@^@^@^@^@\M-0t^@^@^@^@^@^@^@^@^@^@@^@8^@^M^@@^@^]^@^\^@^F^@^@^@^D^@^@^@@^@^@^@^@^@^@^@@^@^@^@^@^@^@^@@^@^@^@^@^@^@^@\M-X^B^@^@^@^@^@^@\M-X^B^@^@^@^@^@^@^H^@^@^@^@^@^@^@^C^@^@^@^D^@^@^@^X^C^@^@^@^@^@^@^X^C^@^@^@^@^@^@^X^C^@^@^@^@^@^@^\^@^@^@^@^@^@^@^\^@^@^@^@^@^@^@^A^@^@^@^@^@^@^@^A^@^@^@^D^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@\M-^H^S^@^@^@^@^@^@\M-^H^S^@^@^@^@^@^@^@^P^@^@^@^@^@^@^A^@^@^@^E^@^@^@^@
/usr/bin/strings:3: unmatched "
/usr/bin/strings:2: parse error in command substitution
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ strings strings| grep  picoCTF
picoCTF{5tRIng5_1T_7f766a23}
```

==picoCTF{5tRIng5_1T_7f766a23}==

## Notas adicionales

## Referencias
Formato ELF
- https://sites.google.com/site/sogrupo15/formato-elf