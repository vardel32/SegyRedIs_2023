# Based
#picoCTF2021 #GeneralSkills 
## Objetivo
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

## Solución
Binario - to ascii
```bash
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
socket
Please give the 01110011 01101111 01100011 01101011 01100101 01110100 as a word.
...
you have 45 seconds.....

Input:
socket
Please give me the  157 166 145 156 as a word.
Input:
oven
Please give me the 6f76656e as a word.
Input:
oven
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}

```

==picoCTF{learning_about_converting_values_b375bb16==
Mediante python se puede convertir de la siguiente forma:
- Binario
```python
┌──(kali㉿kali)-[~]
└─$ python
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> #De binario a ASCII
>>> chr(0b01110011)
's'
>>> chr(0b01101111)
'o'
>>> chr(0b01100011)
'c'
>>> chr(0b01101011)
'k'
>>> chr(0b01100101)
'e'
>>> chr(0b01110100)
't'
```

- Octal
```python
>>> #De octal a ASCII
>>> >>> chr(0o157)
'o'
>>> chr(0o166)
'v'
>>> chr(0o145)
'e'
>>> chr(0o156)
'n'

```

Y para la parte final utilizamos CyberChef con la siguiente receta: `From Hex`.
https://gchq.github.io/CyberChef/#recipe=From_Hex('None')&input=NmY3NjY1NmU
## Notas adicionales

## Referencias
CyberChef
- https://gchq.github.io/CyberChef/