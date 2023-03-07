# Firts Grep
#picoCTF2019 #GeneralSkills 
## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.
## Solución
Primeramente se descarga el archivo mediante `wget`.

```bash
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ wget https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file   
--2023-03-06 23:26:02--  https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 14551 (14K) [application/octet-stream]
Grabando a: «file»

file                 100%[====================>]  14.21K  --.-KB/s    en 0s      

2023-03-06 23:26:03 (210 MB/s) - «file» guardado [14551/14551]

                                                                                  
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ ls
file 
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ file file   
file: ASCII text, with very long lines (4200)

```

Nos encontramos con un archivo de texto bastante largo, contiene 4200 lineas de texto, dentro de las cuales se encuentra la bandera de este nivel.

```bash
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ cat file | grep picoCTF{
picoCTF{grep_is_good_to_find_things_5af9d829}
```

==picoCTF{grep_is_good_to_find_things_5af9d829}==

## Notas adicionales

## Referencias