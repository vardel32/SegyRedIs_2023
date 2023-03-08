# Wave a flag
#picoCTF2021 #GeneralSkills 
## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm) has extraordinarily helpful information...
## Solución
Primeramente nos descargamos el archivo mediante `wget`, analizamos su tipo mediante `file` y al darnos cuenta de que es un archivo ejecutable tipo ELF, mostramos su contenido mediante `strings` y filtramos la bandera mediante `grep`.

```bash
┌──(kali㉿kali)-[~/Downloads/picoCTF2021]
└─$ file warm                            
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=3aa19b2a9cc4e093d64025eab8f510679b523455, with debug_info, not stripped
┌──(kali㉿kali)-[~/Downloads/picoCTF2021]
└─$ strings warm | grep picoCTF{         
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_30e77291}

```

==picoCTF{b1scu1ts_4nd_gr4vy_30e77291}==

## Notas adicionales

## Referencias