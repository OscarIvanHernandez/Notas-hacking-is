# Bandit level 31  → Level 32

## Objetivo
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

## Datos de acceso
bandit31
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Solucion

bandit31@bandit:/tmp/osci$ cd repo
bandit31@bandit:/tmp/osci/repo$ ls
README.md
bandit31@bandit:/tmp/osci/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/osci/repo$ git branch
* master
bandit31@bandit:/tmp/osci/repo$ ls -al
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 23 18:59 .
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 23 18:59 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep 23 18:59 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep 23 18:59 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 Sep 23 18:59 README.md
bandit31@bandit:/tmp/osci/repo$ rm .gitignore
bandit31@bandit:/tmp/osci/repo$ echo "May I come in?" > key.txt
bandit31@bandit:/tmp/osci/repo$ cat key.txt
May I come in?
bandit31@bandit:/tmp/osci/repo$ git add key.txt
bandit31@bandit:/tmp/osci/repo$ git commit -m "añadir key.txt"
[master b69ddab] añadir key.txt
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/osci/repo$ git push

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
bandit31@bandit:/tmp/osci/repo$


## Notas adicionales

## Referencias