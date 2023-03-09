# Glitch Cat
#Beginner_picoMini_2022 #GeneralSkills 
## Objetivo
Our flag printing service has started glitching! `$ nc saturn.picoctf.net 65353`
## Solución
Al conectarnos mediante netcat a la dirección dada nos encontramos con la bandera, la mitad se encuentra en texto ASCII legible y la otra mitad se encuentra escrita en valores hexadecimales. La decodificación se hace utilizando el interprete de python.

```bash
┌──(insoportable㉿kali666)-[~]
└─$ nc saturn.picoctf.net 65353
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
                                                                                                                                                                       
┌──(insoportable㉿kali666)-[~]
└─$ python3
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
'picoCTF{gl17ch_m3_n07_9c42a45d}'
```

==picoCTF{gl17ch_m3_n07_9c42a45d}==
## Notas adicionales

## Referencias