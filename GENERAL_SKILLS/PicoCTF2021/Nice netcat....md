# Nice netcat...
#picoCTF2021 #GeneralSkills 
## Objetivo
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 35652`, but it doesn't speak English...
## Solución
Nos encontramos con un archivo de texto que contiene balores decimales.

```bash
┌──(insoportable㉿kali666)-[/tmp]
└─$ file flag.txt 
flag.txt: ASCII text
┌──(insoportable㉿kali666)-[/tmp]
└─$ head flag.txt 
112 
105 
99 
111 
67 
84 
70 
```

Para poder descrifrar estos elementos desarrollé un script sencillo en python:

```python
bandera = open(flag.txt)
#Se abre el archivo que contiene la bandera cifrada
flag = ''
#Se crea una cadena de texto vacia
for linea in bandera:
#se recorre el archivo con la bandera
	linea = int(linea)
	#cada valor es pasado de str a int
	caracter = chr(linea)
	#El valor entero es transofrmado a caracter
	flag = flag + caracter
	#Se agrega el caracter a la cadena de texto
print(flag)
#Se muestra la bandera
```

Dandonos el siguiente resultado:

```bash
┌──(insoportable㉿kali666)-[/tmp]
└─$ python3 programa.py
picoCTF{g00d_k1tty!_n1c3_k1tty!_9b3b7392}
```

==picoCTF{g00d_k1tty!_n1c3_k1tty!_9b3b7392}==


## Notas adicionales

## Referencias