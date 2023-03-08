# Tab, Tab, Attack
#picoCTF2021 #GeneralSkills 
## Objetivo
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/fe16c756149cfa85f23e73cd9dbd6a25/Addadshashanammu.zip)
## Solución
Se nos proporciona un archivo zip con aproximadamente 7 directorios anidados dentro del mismo, al final del directorio se encuentra un archivo de tipo ELF que como ya sabemos la única manera de extraer información de estos archivos es hacer un comando `cat` concatenado con el comando `strings` para que muestre texto legible mientras que se filtra el contenido mediante `grep`.

```bash
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
                                                                                  
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ ls
Addadshashanammu  Addadshashanammu.zip  file  staticAint  strings
                                                                                  
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ cd Addadshashanammu 
                                                                                  
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills/Addadshashanammu]
└─$ ls
Almurbalarammi
                                                                                  
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills/Addadshashanammu]
└─$ cd Almurbalarammi  
                                                                                  
┌──(insoportable㉿kali666)-[~/…/picoCTF/generalSkills/Addadshashanammu/Almurbalarammi]
└─$ ls
Ashalmimilkala
                                                                                  
┌──(insoportable㉿kali666)-[~/…/picoCTF/generalSkills/Addadshashanammu/Almurbalarammi]
└─$ cd Ashalmimilkala 
                                                                                  
┌──(insoportable㉿kali666)-[~/…/generalSkills/Addadshashanammu/Almurbalarammi/Ashalmimilkala]
└─$ ls
Assurnabitashpi
                                                                                  
┌──(insoportable㉿kali666)-[~/…/generalSkills/Addadshashanammu/Almurbalarammi/Ashalmimilkala]
└─$ cd Assurnabitashpi 
                                                                                  
┌──(insoportable㉿kali666)-[~/…/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi]
└─$ ls
Maelkashishi
                                                                                  
┌──(insoportable㉿kali666)-[~/…/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi]
└─$ cd Maelkashishi   
                                                                                  
┌──(insoportable㉿kali666)-[~/…/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi]
└─$ ls
Onnissiralis
                                                                                  
┌──(insoportable㉿kali666)-[~/…/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi]
└─$ cd Onnissiralis 
                                                                                  
┌──(insoportable㉿kali666)-[~/…/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis]
└─$ ls
Ularradallaku
                                                                                  
┌──(insoportable㉿kali666)-[~/…/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis]
└─$ cd Ularradallaku 
                                                                                  
┌──(insoportable㉿kali666)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls
fang-of-haynekhtnamet
                                                                                  
┌──(insoportable㉿kali666)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=5fffe70019957f0a27a70bb886b2cfb9f9b21d6e, not stripped
                                                                                  
┌──(insoportable㉿kali666)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ cat fang-of-haynekhtnamet|strings|grep picoCTF{
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_76266e38}

```

==picoCTF{l3v3l_up!_t4k3_4_r35t!_76266e38}==

## Notas adicionales

## Referencias