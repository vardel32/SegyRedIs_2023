# Bandit Level 27 → Level 28
#Bandit #OverTheWire 
## Objetivo
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.
## Solución

```bash
bandit27@bandit:~$ mktemp -d
/tmp/tmp.pmv0g8zKjj
bandit27@bandit:~$ cd /tmp/tmp.pmv0g8zKjj
bandit27@bandit:/tmp/tmp.pmv0g8zKjj$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
...
...
...
bandit27@bandit:/tmp/tmp.pmv0g8zKjj$ ls
repo
bandit27@bandit:/tmp/tmp.pmv0g8zKjj$ cd repo
bandit27@bandit:/tmp/tmp.pmv0g8zKjj/repo$ ls
README
bandit27@bandit:/tmp/tmp.pmv0g8zKjj/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR

```

<<<<<<< HEAD
===AVanL161y9rsbcJIsFHuw35rjaOM19nR===

## Notas adicionales
mktemp -d crea una carpeta con un nombre al azar
=======
## Notas adicionales
mktemp -d
>>>>>>> 8e322873663603679adefd9d4cd7105c0f8737e3
## Referencias