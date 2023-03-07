# Lets Warm Up
#picoCTF2019 #GeneralSkills 
## Objetivo
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?
## Solución
```bash
┌──(insoportable㉿kali666)-[~]
└─$ printf '\x70' 
p  
```
picoCTF[p]
## Notas adicionales
El comando `printf` posee distintos especificadores de formato, en esta ocasión se utiliza el especificador de fomrato `\x` para representar un numero hexadecimal
## Referencias
Convert Hex to ASCII
-  https://www.baeldung.com/linux/character-hex-to-ascii