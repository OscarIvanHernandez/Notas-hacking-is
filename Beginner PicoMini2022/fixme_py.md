# Beginner PicoMini2022
## Objetivo
Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/37/fixme1.py)
## Pistas
To view the file in the webshell, do: `$ nano fixme1.py`
## Solucion
┌─[oscar@oscar-parrot]─[~]
└──╼ $python3 fixme1.py 
  File "/home/oscar/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $nano fixme1.py 
┌─[oscar@oscar-parrot]─[~]
└──╼ $python3 fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}
┌─[oscar@oscar-parrot]─[~]
└──╼ $
## Notas adicionales
El error fue la identacion de la linea seleccionada en la captura

## Referencias
https://www.youtube.com/watch?v=UTLFMjrMfa8
