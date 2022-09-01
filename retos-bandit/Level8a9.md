# Bandit level 8 → Level 9

## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Datos de acceso
bandit8
cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Solucion
bandit8@bandit:~$ cat data.txt | sort | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
bandit8@bandit:~$ exit
## Notas adicionales
Abriendo el archivo se ordena el contenido con sort y se obtiene la unica linea que no se repite entre elllas

## Referencias
