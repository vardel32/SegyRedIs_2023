# PW Crack 2
#Beginner_picoMini_2022 #GeneralSkills 
## Objetivo
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/16/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level2.flag.txt.enc) in the same directory too.
## Solución
En el archivo que se encarga de corroborar la contrasñea una vez más nos es dada la contraseña, sin embargo ahora en formato hexadecimal

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

flag_enc = open('level2.flag.txt.enc', 'rb').read()
def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
level_2_pw_check()

```

El archivo se modifica y una vez más se le asigna a la variable `user_pw` la contraseña dada dentro del programa.

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
flag_enc = open('level2.flag.txt.enc', 'rb').read()
def level_2_pw_check():
    user_pw = (chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36))
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
level_2_pw_check()
```

```bash
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills/pwcrack2]
└─$ python3 level2.py
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
```

==picoCTF{tr45h_51ng1ng_489dea9a}==

## Notas adicionales

## Referencias