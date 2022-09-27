# Beginner PicoMini2022
## Objetivo
Fix the syntax error in the Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/66/fixme2.py)
## Pistas
Are equality and assignment the same symbol?
## Solucion
┌─[oscar@oscar-parrot]─[~]
└──╼ $python3 fixme2.py 
  File "/home/oscar/fixme2.py", line 22
    if flag = "":
            ^
SyntaxError: invalid syntax
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $nano fixme2.py 
┌─[oscar@oscar-parrot]─[~]
└──╼ $python3 fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
┌─[oscar@oscar-parrot]─[~]
└──╼ $

## Notas adicionales
El error era en el simbolo de comparacion dentro un if( ), se estaba haciendo una asignacion 
## Referencias