# Bandit level 20 → Level 21

## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

## Datos de acceso

VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solucion

bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Sep  1 06:30 .
drwxr-xr-x 49 root     root      4096 Sep  1 06:30 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15596 Sep  1 06:30 suconnect
bandit20@bandit:~$ nc -lvp 3030 <<<
-bash: syntax error near unexpected token `newline'
bandit20@bandit:~$ nc -lvp 3030 <<<
-bash: syntax error near unexpected token `newline'
bandit20@bandit:~$ nc -lvp 2020 <<<
-bash: syntax error near unexpected token `newline'
bandit20@bandit:~$ nc -lvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Listening on 0.0.0.0 2020
^Z
[1]+  Stopped                 nc -lvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ ./suconnect 2020
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
bandit20@bandit:~$ ./suconnect 2020
^C
bandit20@bandit:~$ nc -lvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Listening on 0.0.0.0 2020
^C
bandit20@bandit:~$ ./suconnect 2020
^Z
[2]+  Stopped                 ./suconnect 2020
bandit20@bandit:~$

## Notas adicionales

## Referencias
