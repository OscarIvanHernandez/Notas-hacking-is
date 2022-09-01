# Bandit level 1 → Level 2

## Objetivo
The password for the next level is stored in a file called **-** located in the home directory

## Datos de acceso
bandit1
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
## Solucion
bandit1@bandit:~$ cat readme
cat: readme: No such file or directory
bandit1@bandit:~$ l
-bash: l: command not found
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ file readme
readme: cannot open `readme' (No such file or directory)
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
bandit1@bandit:~$ exit

## Notas adicionales
En unix o linux, el dash (-) es usado generalmente en especificar opciones y argumentos, para acceder a un archivo en este caso nombrado con un dash, se debe especificar la ruta de donde se ecunetra ese archivo.

## Referencias
https://www.webservertalk.com/dashed-filename#:~:text=Dashed%20Filename%20%E2%80%93%20Learn%20How%20to,%2C%20List%2C%20Read%20%26%20Copy!&text=In%20Unix%20or%20Linux%20operating,to%20specify%20options%20and%20arguments.
