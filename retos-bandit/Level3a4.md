# Bandit  level 3 → Level 4

## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.

## Datos de acceso
bandit3
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
## Solucion
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 May  7  2020 .
drwxr-xr-x 3 root    root    4096 May  7  2020 ..
-rw-r----- 1 bandit4 bandit3   33 May  7  2020 .hidden
bandit3@bandit:~/inhere$ cat ./.hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
bandit3@bandit:~/inhere$

## Notas adicionales
Usando ls y añadiendo -la ( l (use a long listing format), a (all files including ones with a dot prefix)) dentro del directorio, nos podemos percatar del tipo de archivo que es y por ende acceder (cat ./.hidden)

## Referencias
https://man7.org/linux/man-pages/man1/ls.1.html
https://jwuk.files.wordpress.com/2016/05/writeup1.pdf
