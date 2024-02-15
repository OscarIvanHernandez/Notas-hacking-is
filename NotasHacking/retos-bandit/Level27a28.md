# Bandit level 27  → Level 28

## Objetivo
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## Datos de acceso

bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solucion
bandit27@bandit:~$ mkdir /tmp/osc_hhgit
bandit27@bandit:~$ cd /tmp/osc_hhgit
bandit27@bandit:/tmp/osc_hhgit$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
bandit27-git@localhost's password:

...

bandit27@bandit:/tmp/osc_hhgit$ ls -la
total 196
drwxrwxr-x    3 bandit27 bandit27   4096 Sep  6 14:29 .
drwxrwx-wt 4870 root     root     188416 Sep  6 14:28 ..
drwxrwxr-x    3 bandit27 bandit27   4096 Sep  6 14:29 repo
bandit27@bandit:/tmp/osc_hhgit$
bandit27@bandit:/tmp/osc_hhgit$ cd repo
bandit27@bandit:/tmp/osc_hhgit/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/osc_hhgit/repo$

## Notas adicionales

## Referencias