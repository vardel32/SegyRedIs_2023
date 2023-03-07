# plumbingTitulo
#picoCTF2021 #GeneralSkills 
## Objetivo
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.
## Solución
Al momento de ejecutar la conexión se ejecuta un script que nos devuelve el contenido de un archivo de texto bastante grande.

```bash
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 4427
This is defintely not a flag
Not a flag either
I don't think this is a flag either
Not a flag either
...
...
...
...
```

Sin embargo NetCat permite ejecutar comandos junto con la conexión establecida. De esta manera ejecutamos un comando `grep` que nos permita filtrar el contenido mostrado.

```bash
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 4427 | grep picoCTF{
picoCTF{digital_plumb3r_5ea1fbd7}
```

==picoCTF{digital_plumb3r_5ea1fbd7}==

## Notas adicionales

## Referencias