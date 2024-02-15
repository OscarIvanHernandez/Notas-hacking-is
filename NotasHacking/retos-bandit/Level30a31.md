# Bandit level 30 → Level 31

## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Datos de acceso
bandit30
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solucion

bandit30@bandit:~$ mkdir /tmp/osr_
bandit30@bandit:~$ cd /tmp/osr_
bandit30@bandit:/tmp/osr_$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo

...


bandit30@bandit:/tmp/osr_$ cd repo
bandit30@bandit:/tmp/osr_/repo$ ls
README.md
bandit30@bandit:/tmp/osr_/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/osr_/repo$ git log
commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md
bandit30@bandit:/tmp/osr_/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/master
bandit30@bandit:/tmp/osr_/repo$ git branch
* master
bandit30@bandit:/tmp/osr_/repo$ git log
commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md
bandit30@bandit:/tmp/osr_/repo$ git tag
secret
bandit30@bandit:/tmp/osr_/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/osr_/repo$

## Notas adicionales

## Referencias