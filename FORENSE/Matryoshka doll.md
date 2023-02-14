# Matryoshka doll
#picoCTF2021 #FORENSICS 
## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/f6cc2560a70b1ea811c151accba5390f/dolls.jpg)

## Solución
Se nos da la siguiente imagen:

![[Pasted image 20221227174355.png]]

Al ejecutar la herramienta `Binwalk` Podemos ver que la imágen contiene un archivo ZIP que puede ser extraido.

```bash
┌──(kali㉿kali)-[~/Downloads/forense]
└─$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378955, uncompressed size: 383936, name: base_images/2_c.jpg
651613        0x9F15D         End of Zip archive, footer length: 22

    
```

Mediante la opcion '-e' de Binwalk podemos extraer los archivos embebidos, crear una carpeta especifica y almacenar dichos archivos en esa carpeta.

```bash
┌──(kali㉿kali)-[~/Downloads/forense]
└─$ binwalk -e dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378955, uncompressed size: 383936, name: base_images/2_c.jpg
651613        0x9F15D         End of Zip archive, footer length: 22

                                                                                  
┌──(kali㉿kali)-[~/Downloads/forense]
└─$ ls
dolls.jpg  _dolls.jpg.extracted

```

Dentro de la carpeta creada se encuentra una segunda carpeta con una nueva imagen, en esta imagen se encuentra incrustado otro archivo zip. Tras volver a sacar el archivo ZIP nos volvemos a enonctrar con otra imagen, haciendo así alución al nombre del reto, son imagenes dentro de imagenes.
El proceso de extraer archivos zip de las imagenes es hecho un total de 4 ocasiones, al final se encuentra un archivo .txt que contiene la bandera 

```bash
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted 
                                                                                  
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls                   
136DA.zip  flag.txt
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt
picoCTF{ac0072c423ee13bfc0b166af72e25b61}   

```

==picoCTF{ac0072c423ee13bfc0b166af72e25b61}==

## Notas adicionales
Binwalk es una herramienta forense destinada a la extracción de datos de imagenes binarias de firmware (proceso más conocido como "_Firmware hacking_"). Puede ser utizada para analizar en busqueda de código malicioso, relizar ingeniería inversa.
## Referencias
- Binwalk 
  https://www.kali.org/tools/binwalk/