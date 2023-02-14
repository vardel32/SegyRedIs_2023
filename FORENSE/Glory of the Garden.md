# Glory of the Garden
#picoCTF2021 #FORENSICS 
## Objetivo
This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.
## Solución
Nos encontramos con un archivo JPEG, es decir una **imagen** cuyo contenido es la fotografía de un jardin.
![[Pasted image 20221231201845.png|500]]

Analizando los metadatos de la imagen, mediante el comando `exiftool` no se ha encontrado información satisfactoria.
La herramienta `hexeditor` de linux ademas de editar los datos hexadecimales de los archivos y buscar posiciones de offsets, permite buscar textos en formato `String`, es decir, palabras textuales como las que conforman el formato de la bandera utilizado para la plataforma picoCTF.
Así mediante esta herramienta encontramos que la bandera está incrustada en los datos hexadecimales de la imagen, y comienza en el offset 0x0023056.
==picoCTF{more_than_m33ts_the_3y33dd2eEF5}==

```bash
File: garden.jpg                    ASCII Offset: 0x0023056E / 0x00230597 (%100) 
00230560  72 65 20 69  73 20 61 20   66 6C 61 67  20 22 70 69     re is a flag "pi
00230570  63 6F 43 54  46 7B 6D 6F   72 65 5F 74  68 61 6E 5F     coCTF{more_than_
00230580  6D 33 33 74  73 5F 74 68   65 5F 33 79  33 33 64 64     m33ts_the_3y33dd
00230590  32 65 45 46  35 7D 22 0A                                2eEF5}".

```
## Notas adicionales
La herramienta utilizada para dar solucion es `hexeditor`, sobre el cual se aplica el comando `ctrl w` para entrar en el menú de busqueda. Existen tres opciones en este menú, se selecciona `search for text string` para buscar cadenas de texto entre los valores hexadecimales de los datos del archivo dado.
## Referencias
https://en.wikipedia.org/wiki/List_of_file_signatures