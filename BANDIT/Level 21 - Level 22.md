# Bandit Level 21 → Level 22
#Bandit #OverTheWire 
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
## Solución
Al mirar dentro del directorio indicado, nos podemos encontar con un cronjob del usuario bandit 22. Observamos que es un archivo de texto entonces se puede leer mediante el comando `cat`.
Al leer el cronjob nos damos cuenta de que se redirige la salida del archivo `/usr/bin/cronjob_bandit22.sh` al directorio `/dev/null`.
Al investigar el archivo descubrimos que es un bash script que transfiere el contenido de la carpeta de contraseñas al directorio `/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv.
Haciendo un comando `cat` a ese archivo en particular, obtenemos la contraseña.

```bash
bandit21@bandit:~$ cd /etc/cron.d/
bandit21@bandit:/etc/cron.d$ ls
cronjob_bandit15_root  cronjob_bandit23       e2scrub_all
cronjob_bandit17_root  cronjob_bandit24       otw-tmp-dir
cronjob_bandit22       cronjob_bandit25_root  sysstat
bandit21@bandit:/etc/cron.d$ file cronjob_bandit22
cronjob_bandit22: ASCII text
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:/etc/cron.d$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

```

===WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff===
## Notas adicionales
`&>` redirige la salida del primer comando hacia el segundo comando
## Referencias
- &> https://stackoverflow.com/questions/24793069/what-does-do-in-bash