# Bandit level 28  → Level 29

## Objetivo
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

## Datos de acceso
bandit28
AVanL161y9rsbcJIsFHuw35rjaOM19nR

## Solucion

bandit28@bandit:~$ mkdir /tmp/oscar__
bandit28@bandit:~$ cd /tmp/oscar__
bandit28@bandit:/tmp/oscar__$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo

...


bandit28@bandit:/tmp/oscar__$ cd repo
bandit28@bandit:/tmp/oscar__/repo$ cat README
cat: README: No such file or directory
bandit28@bandit:/tmp/oscar__/repo$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Sep 23 16:26 .
drwxrwxr-x 3 bandit28 bandit28 4096 Sep 23 16:26 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Sep 23 16:26 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Sep 23 16:26 README.md
bandit28@bandit:/tmp/oscar__/repo$ cat README.md
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/oscar__/repo$ git log
commit 43032edb2fb868dea2ceda9cb3882b2c336c09ec (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    fix info leak

commit bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    add missing data

commit 43d032b360b700e881e490fbbd2eee9eccd7919e
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:24 2022 +0000

    initial commit of README.md
bandit28@bandit:/tmp/oscar__/repo$ git branch
* master
bandit28@bandit:/tmp/oscar__/repo$ git checkout bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
Note: switching to 'bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at bdf3099 add missing data
bandit28@bandit:/tmp/oscar__/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

bandit28@bandit:/tmp/oscar__/repo$



## Notas adicionales

## Referencias