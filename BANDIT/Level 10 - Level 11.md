# Bandit Level 10 → Level 11
#Bandit #OverTheWire 
## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Solución
Se encuentra un archivo de texto con la bandera cifrada en base64.

```bash
bandit10@bandit:~$ ls 
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
```

Utilizando cyberchef podemos decodificar el texto, dandonos el siguiente contenido.
`The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM`
==6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM==
## Notas adicionales

## Referencias
- Cyberchef https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQwYUdWZmJUTjBZV1JoZEdGZk1YTmZiVzlrYVdacFpXUjk