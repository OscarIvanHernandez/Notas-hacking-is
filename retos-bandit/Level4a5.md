# Bandit level 4 → Level 5

## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Datos de acceso
bandit4
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
## Solucion
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ cat ./file00
cat: ./file00: No such file or directory
bandit4@bandit:~/inhere$ cat ./-file02
e)#5pV_ׯmmbandit4@bandit:~/inhere$ cat ./-file05
rl$?h9('!ye#xO=bandit4@bandit:~/inhere$ cat ./-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
bandit4@bandit:~/inhere$ exit


## Notas adicionales

## Referencias
