tunn3l v1s10n
#picoCTF2021 #FORENSICS 
## Objetivo
We found this [file](https://mercury.picoctf.net/static/06a5e4ab22ba52cd66a038d51a6cc07b/tunn3l_v1s10n). Recover the flag.
## Solución
Si mostramos los datos mediante xxd podemos comprobar que tenemos un archivo BMP dañado, se trata de un BitMap para windows.

```bash
┌──(kali㉿kali)-[~/Downloads/forense]
└─$ xxd tunn3l_v1s10n | head
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/
00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v
00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT
00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.
                            
```

Dado que se trata de un BMP para windows nuestro encabezado debe de ser de 40 bits, 28 en hexadecimal. El tamaño del encabezado para los archivos BMP es indicado en la posición "0E".
Se observa que en la posicion 0E se encuentran los caracteres "BA D" indicando el error.Se reemplazan por "28 0"
En la posicion "0A" nos encontramos con otro "BA D", en esta posición se coloca el inicio de los datos.
![[Pasted image 20221227204807.png]]
En este caso el inicio de los datos es "28" pues después del encabezado comienzan los datos, así que se corrige de igual manera.
![[Pasted image 20221227204058.png]]
Sin embargo no es suficiente, la altura de la imgen parece ser reducida para una imagen de ese peso en megabytes, en el offset "16" se almacena la información de la altura de las imagenes BMP
modificamos los valores por "4004" y podemos ver que la imagen ya cuenta con una altura y un ancho que le dan forma cuadrada.

```bash
┌──(kali㉿kali)-[~/Downloads/forense]
└─$ exiftool tunn3l_v1s10n.bpm 
ExifTool Version Number         : 12.49
File Name                       : tunn3l_v1s10n.bpm
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 1088
Image Size                      : 1134x1088

```

De esta manera obtenemos la imagen con la bandera.
![[Pasted image 20221227210018.png]]

==picoCTF{qu1t3_a_v13w_2020}==
## Notas adicionales
- **Windows bitmap (.BMP)** es un formato del ITSL [imagen de mapa de bits](https://es.wikipedia.org/wiki/Imagen_de_mapa_de_bits "Imagen de mapa de bits"), propio del sistema operativo [Microsoft Windows](https://es.wikipedia.org/wiki/Microsoft_Windows "Microsoft Windows"). Puede guardar imágenes de 24 bits (16,7 millones de colores), 8 bits (256 tonos de gris) y menos.
## Referencias
https://en.wikipedia.org/wiki/BMP_file_format