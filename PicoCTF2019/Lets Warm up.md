# PICOCTF2019

## Descripcion
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Datos de acceso

## Solucion
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $python3.9
Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii("\x70")
"'p'"
>>> exit
Use exit() or Ctrl-D (i.e. EOF) to exit
>>> 
┌─[oscar@oscar-parrot]─[~]
└──╼ $^C



## Notas adicionales

## Referencias
https://www.geeksforgeeks.org/ascii-in-python/
