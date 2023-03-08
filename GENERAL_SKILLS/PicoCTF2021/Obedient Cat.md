# Obedient Cat
#picoCTF2021 #GeneralSkills 
## Objetivo
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag).
## Solución
Se descarga el archivo mediante `Wget` y lo analizamos con `file` para saber que tipo de archivo es. Posteriormente al darnos cuenta de que es un archivo de texto ASCII mostramos su contenido mediante `cat`.

```bash
┌──(kali㉿kali)-[~/Downloads/picoCTF2021]
└─$ wget https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag
--2023-03-07 14:06:27--  https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: ‘flag’

flag                 100%[====================>]      34  --.-KB/s    in 0s      

2023-03-07 14:06:35 (59.9 MB/s) - ‘flag’ saved [34/34]

                                                                                  
┌──(kali㉿kali)-[~/Downloads/picoCTF2021]
└─$ ls
flag
                                                                                  
┌──(kali㉿kali)-[~/Downloads/picoCTF2021]
└─$ file flag
flag: ASCII text
                                                                                  
┌──(kali㉿kali)-[~/Downloads/picoCTF2021]
└─$ cat flag      
picoCTF{s4n1ty_v3r1f13d_2aa22101}
```

De esta manera obtenemos la bandera.

==picoCTF{s4n1ty_v3r1f13d_2aa22101}==

## Notas adicionales

## Referencias