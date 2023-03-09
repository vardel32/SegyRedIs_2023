# convertme.py
#Beginner_picoMini_2022 #GeneralSkills 
## Objetivo
Run the Python script and convert the given number from decimal to binary to get the flag. [Download Python script](https://artifacts.picoctf.net/c/32/convertme.py)
## Solución
Nos encontramos con el siguiente programa de python:

```python
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5f) + chr(0x05) + chr(0x08) + chr(0x2a) + chr(0x1c) + chr(0x5e) + chr(0x1e) + chr(0x1b) + chr(0x3b) + chr(0x17) + chr(0x51) + chr(0x5b) + chr(0x58) + chr(0x5c) + chr(0x3b) + chr(0x42) + chr(0x57) + chr(0x5c) + chr(0x0d) + chr(0x5f) + chr(0x06) + chr(0x46) + chr(0x5c) + chr(0x13)


num = random.choice(range(10,101))

print('If ' + str(num) + ' is in decimal base, what is it in binary base?')

ans = input('Answer: ')

try:
  ans_num = int(ans, base=2)
  
  if ans_num == num:
    flag = str_xor(flag_enc, 'enkidu')
    print('That is correct! Here\'s your flag: ' + flag)
  else:
    print(str(ans_num) + ' and ' + str(num) + ' are not equal.')
  
except ValueError:
  print('That isn\'t a binary number. Binary numbers contain only 1\'s and 0\'s')
```

Nos encontramos con dos formas de solucionar el problema
- La primera es modificar el código ya que dentro del código se encuentra  la bandera cifrada en la variable `flag_enc` junto con una función para descifrarla junto con la clave `def str_xor(secret, key)`, `def str_xor(secret, key)`.
- La segunda forma de solucionar el reto consiste en hacer lo que efectivamente nos pide el programa y hacer la conversión de decimal a binario.
Decicdí probar ambos métodos, naturalmente el más sencillo es hacer la simple conversión.

El script modificado para dar la bandera automaticamente es el siguiente:

```python
import random
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5f) + chr(0x05) + chr(0x08) + chr(0x2a) + chr(0x1c) + chr(0x5e) + chr(0x1e) + chr(0x1b) + chr(0x3b) + chr(0x17) + chr(0x51) + chr(0x5b) + chr(0x58) + chr(0x5c) + chr(0x3b) + chr(0x42) + chr(0x57) + chr(0x5c) + chr(0x0d) + chr(0x5f) + chr(0x06) + chr(0x46) + chr(0x5c) + chr(0x13)


flag = str_xor(flag_enc, 'enkidu')
print('Bandera mediante el crackeo del programa:\n' + flag)
```

```bash
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ python3 convertme2.py
Bandera mediante el crackeo del programa:
picoCTF{4ll_y0ur_b4535_722f6b39}

```

La solución habitual es la siguiente y se ejecuta con la función 
```bash
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ python3 convertme.py
If 84 is in decimal base, what is it in binary base?
Answer: 1010100
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_722f6b39}
```

```python
>>> bin(84)
'0b1010100'
```

==picoCTF{4ll_y0ur_b4535_722f6b39}==
## Notas adicionales

## Referencias