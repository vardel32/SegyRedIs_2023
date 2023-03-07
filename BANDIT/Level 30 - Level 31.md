# Bandit Level 30 → Level 31
#Bandit #OverTheWire 
## Objetivo
There is a git repository at `ssh://bandit30-git@localhost:2220/home/bandit30-git/repo`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.
## Solución

```bash
bandit30@bandit:~$ mktemp -d
/tmp/tmp.bDQFWsWjBH
bandit30@bandit:~$ cd /tmp/tmp.bDQFWsWjBH
bandit30@bandit:/tmp/tmp.bDQFWsWjBH$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
...
...
...
bandit30@bandit:/tmp/tmp.bDQFWsWjBH$ cd repo
bandit30@bandit:/tmp/tmp.bDQFWsWjBH/repo$ 
bandit30@bandit:/tmp/tmp.bDQFWsWjBH/repo$ ls
README.md
bandit30@bandit:/tmp/tmp.bDQFWsWjBH/repo$ cat README.md 
just an epmty file... muahaha

bandit30@bandit:/tmp/tmp.bDQFWsWjBH/repo/.git$ git tag
secret
bandit30@bandit:/tmp/tmp.bDQFWsWjBH/repo/.git$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/tmp.bDQFWsWjBH/repo/.git$ exit

```

===OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt===

## Notas adicionales
Las etiquetas (`tag`)  son referencias que apuntan a puntos concretos del historial de Git. Habitualmente el etiquetado se usa para capturat un punto en el historial que se utiliza para una publicación de version marcada.

## Referencias
https://www.atlassian.com/es/git/tutorials/inspecting-a-repository/git-tag#:~:text=El%20comando%20git%20tag%20es,valiosos%20adicionales%20sobre%20la%20etiqueta.