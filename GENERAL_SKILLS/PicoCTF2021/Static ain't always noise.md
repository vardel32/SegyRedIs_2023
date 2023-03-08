# Static ain't always noise
#picoCTF2021 #GeneralSkills 
## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static)? This [BASH script](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh) might help!
## Solución
Nos encontramos con un archivo de formato ELF, es decir un ejecutable, si le hacemos `cat` mostrará texto ilegible. Esto se soluciona utilizando el comando `strings` que muestra el texto legible y filtramos lo mostrado con un comando `grep`.


```bash
┌──(insoportable㉿kali666)-[~/Descargas/picoCTF/generalSkills/staticAint]
└─$ cat static| strings | grep picoCTF{
picoCTF{d15a5m_t34s3r_f6c48608}
```

==picoCTF{d15a5m_t34s3r_f6c48608}==

## Notas adicionales

## Referencias