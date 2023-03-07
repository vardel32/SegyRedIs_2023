# Bandit Level 31 → Level 32
#Bandit #OverTheWire 
## Objetivo
There is a git repository at `ssh://bandit31-git@localhost:2220/home/bandit31-git/repo`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.
## Solución

```bash
bandit31@bandit:~$ 
bandit31@bandit:~$ mktemp -d
/tmp/tmp.B4bRjUZMTS
bandit31@bandit:~$ cd /tmp/tmp.B4bRjUZMTS
bandit31@bandit:/tmp/tmp.B4bRjUZMTS$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
...
...
...
...
bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Mar  5 00:08 .
drwx------ 3 bandit31 bandit31 4096 Mar  5 00:08 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Mar  5 00:08 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Mar  5 00:08 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 Mar  5 00:08 README.md
bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$ cat .gitignore
*.txt
bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$
bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$ rm .gitignore
bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Mar  5 00:12 .
drwx------ 3 bandit31 bandit31 4096 Mar  5 00:08 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Mar  5 00:08 .git
-rw-rw-r-- 1 bandit31 bandit31   15 Mar  5 00:11 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Mar  5 00:08 README.md
bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$ git add .
bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$ git commit -m 'push bandit 31'
[master d7e334a] push bandit 31
 2 files changed, 1 insertion(+), 1 deletion(-)
 delete mode 100644 .gitignore
 create mode 100644 key.txt
bandit31@bandit:/tmp/tmp.B4bRjUZMTS/repo$ git push
...
...
...
...
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y 
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'

```

===rmCBvG56y58BXzv98yZGdO7ATVL5dW8y===
## Notas adicionales

## Referencias
https://atareao.es/tutorial/terminal/redirigir-entrada-y-salida-en-linux/