# Bandit Level 29 → Level 30
#Bandit #OverTheWire 
## Objetivo
There is a git repository at `ssh://bandit29-git@localhost:2220/home/bandit29-git/repo`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.
## Solución
En esta ocasión no hubi filtraciones en producción.

```bash
bandit29@bandit:~$ mktemp -d
/tmp/tmp.efAj7qXhCX
bandit29@bandit:~$ cd /tmp/tmp.efAj7qXhCX
bandit29@bandit:/tmp/tmp.efAj7qXhCX$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
...
...
...
bandit29@bandit:/tmp/tmp.efAj7qXhCX$ cd repo
bandit29@bandit:/tmp/tmp.efAj7qXhCX/repo$ 
bandit29@bandit:/tmp/tmp.efAj7qXhCX/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>
```

Sin embargo si revisamos los logs podemos ver que se han hecho commits en la rama `dev`:

```bash
bandit29@bandit:/tmp/tmp.efAj7qXhCX/repo/.git$ git log -p
commit 0afe3501277395fbfa017480925edee3df6e8bb5 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:11 2023 +0000

    fix username

diff --git a/README.md b/README.md
index 2da2f39..1af21d3 100644
--- a/README.md
+++ b/README.md
@@ -3,6 +3,6 @@ Some notes for bandit30 of bandit.
 
 ## credentials
 
-- username: bandit29
+- username: bandit30
 - password: <no passwords in production!>
 

commit c2606dfc0aef7179bf1ccd6cffa9ed19151facb4
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:11 2023 +0000

    initial commit of README.md

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..2da2f39
```

Así que se hace un cambio a la rama `dev` y observamos los logs:

```bash
bandit29@bandit:/tmp/tmp.efAj7qXhCX/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/dev
  origin/master
  origin/sploits-dev
bandit29@bandit:/tmp/tmp.efAj7qXhCX/repo$ git log -p
commit fbbce0ec6c80acb0fdc00ebb4b5228dd868fd799 (HEAD -> dev, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Tue Feb 21 22:03:11 2023 +0000

    add data needed for development

diff --git a/README.md b/README.md
index 1af21d3..a4b1cf1 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
 ## credentials
 
 - username: bandit30
-- password: <no passwords in production!>
+- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
 

commit 925c929e0527f14c189b3d617d2bcc60f019f567
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:11 2023 +0000

    add gif2ascii

diff --git a/code/gif2ascii.py b/code/gif2ascii.py
new file mode 100644
index 0000000..8b13789
--- /dev/null
+++ b/code/gif2ascii.py
bandit29@bandit:/tmp/tmp.efAj7qXhCX/repo$ 


```

===xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS===

## Notas adicionales
Es importante recalcar que si se intenta cambiar de branch estando dentro de la carpeta `.git` el comando lanzará un error como el siguiente:

```bash
bandit29@bandit:/tmp/tmp.efAj7qXhCX/repo/.git$ git checkout dev
fatal: this operation must be run in a work tree

```

Por lo tanto los cambios de branch deben hacerse desde la carpeta raíz del repositorio.


## Referencias
https://stackoverflow.com/questions/1456923/why-am-i-getting-the-message-fatal-this-operation-must-be-run-in-a-work-tree