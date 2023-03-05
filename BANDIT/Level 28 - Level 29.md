# Titulo
#Bandit #OverTheWire 
## Objetivo
There is a git repository at `ssh://bandit28-git@localhost:2220/home/bandit28-git/repo`. The password for the user `bandit28-git` is the same as for the user `bandit28`.
Clone the repository and find the password for the next level.
## Solución
```bash
bandit28@bandit:~$ mktemp -d
/tmp/tmp.Mwua85HKd1
bandit28@bandit:~$ cd /tmp/tmp.Mwua85HKd1
bandit28@bandit:/tmp/tmp.Mwua85HKd1$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
...
...
...
...
bandit28@bandit:/tmp/tmp.Mwua85HKd1$ cd repo
bandit28@bandit:/tmp/tmp.Mwua85HKd1/repo$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Mar  4 21:29 .
drwx------ 3 bandit28 bandit28 4096 Mar  4 21:28 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Mar  4 21:29 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Mar  4 21:29 README.md
bandit28@bandit:/tmp/tmp.Mwua85HKd1/repo$ 
bandit28@bandit:/tmp/tmp.Mwua85HKd1/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx


```

Podemos observar que existe un archivo en el cual se pudo haber almacenado la contraseña de bandit29. Mediante el comando `git log -p` podemos ver los registros de los archivos modificados.

```bash
commit 6c3c5e485cc531e5d52c321587ce1103833ab7c3
Author: Morla Porla <morla@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    add missing data

diff --git a/README.md b/README.md
index 7ba2d2f..b302105 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials
 
 - username: bandit29
-- password: <TBD>
+- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
ommit 104db85a904e9691ff22aafe1a96124c88f75afa (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    fix info leak

diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials
 
 - username: bandit29
-- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
+- password: xxxxxxxxxx
 

commit 6c3c5e485cc531e5d52c321587ce1103833ab7c3
Author: Morla Porla <morla@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    add missing data

diff --git a/README.md b/README.md
index 7ba2d2f..b302105 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.

```

Se puede observar que se modifico el archivo `README.md`. Este archivo contenia la contraseña de bandit29 en su creación.

===tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S===
## Notas adicionales
El comando `git log -p` o `git log --patch` ocasiona que git muestre los archivos modificados, la locación de los arhcivos que fueron agregados o eliminados, y cambios especificos que se han hecho.
## Referencias
https://www.freecodecamp.org/news/git-log-command/#:~:text=The%20git%20log%20command%20displays,author