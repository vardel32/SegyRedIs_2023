# Bandit Level 22 → Level 23
#OverTheWire #Bandit 
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
## Solución

```bash
bandit22@bandit:/etc/cron.d$ cat cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:/etc/cron.d$ myname=bandit23
bandit22@bandit:/etc/cron.d$ echo $(echo I am user $myname | md5sum | cut -d ' ' -f 1)
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:/etc/cron.d$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

```

===QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G===

## Notas adicionales
- `md5sum` en esta ocasión es utilizado para generar un hash utilizando el texto "I am user bandit23"
- El comando `cut` es bastante útil para eliminar secciones, campos o caracteres de la salida de un comando o de las lineas de un fichero de texto.
	- El parametro `-d` es utilizado para `delimitar` el texto que se quiere tomar, en esta ocasión el delimitador utilizado es el espacio en blanco `' '`
	- El parametro `-f 1` se utiliza para mostrar solo la primera palabra
## Referencias
- md5sum https://www.linuxtotal.com.mx/index.php?cont=info__tips_004#:~:text=Pues%20ahí%20tienes%20md5sum%20una,de%20Linux%20o%20sus%20servicios%3F
	- `md5sum` te puede servir para generar hashes de contraseñas, tan solo invoca `md5sum` sin argumentos
- cut https://geekland.eu/uso-del-comando-cut-en-linux-y-unix-con-ejemplos/
	- https://man7.org/linux/man-pages/man1/cut.1.html