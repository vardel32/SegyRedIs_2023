# PW Crack 1
#Beginner_picoMini_2022 #GeneralSkills 
## Objetivo
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/53/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/53/level1.flag.txt.enc) in the same directory too.
## Solución
Se nos proporciona un archivo con la bandera encriptada y un programa en python que recibe una contraseña y si es la contraseña esperada devuelve la bandera.

```python
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################
flag_enc = open('level1.flag.txt.enc', 'rb').read()
def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "8713"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
level_1_pw_check()
```

Existen dos maneras de resolver el reto, la primera y más sencilla es observar el contenido del programa que desencripta la bandera, en la sentencia `if` que corrobora la contraseña, se encuentra la propia contraseña `if( user_pw == "8713")`.

La segunda manera es modificar el archivo y asignar a la variable `user_pw` el valor requerido:

```python
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################
flag_enc = open('level1.flag.txt.enc', 'rb').read()
def level_1_pw_check():
    user_pw = "8713"
    if(user_pw == "8713"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
level_1_pw_check()
```

```bash
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills]
└─$ python3 level1.py
El archivo ha sido modificado para dar la bandera automaticamente:

picoCTF{545h_r1ng1ng_1b2fd683}

```

==picoCTF{545h_r1ng1ng_1b2fd683}==

## Notas adicionales

## Referencias