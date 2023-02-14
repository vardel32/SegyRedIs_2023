# So Meta
#pico2019 #FORENSICS 
## Objetivo
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).
## Solución
Nos encontramos con una imagen en formato PNG, de 600 pixeles por 600. Segun las pistas dadas por la plataforma pico la bandera se encuentra relacionada a los metadatos de la imagen.

![[Pasted image 20230106205603.png|400]]

Ejecutando el comando `exiftool` podemos acceder a los metadatos de la imagen en cuestion obteniendo la siguiente información importante...
```bash
┌──(kali㉿kali)-[~/Downloads/forense/someta]
└─$ exiftool pico_img.png 
Artist                          : picoCTF{s0_m3ta_d8944929}

```

La bandera se encontraba incrustada en los metadatos relacionados al artista de la imagen.
Bandera:
===picoCTF{s0_m3ta_d8944929}===

## Notas adicionales
Los metadatos de un archivo son datos que describen otros datos. Es decir, datos que describen el contenido informativo del archivo en cuestion.
## Referencias