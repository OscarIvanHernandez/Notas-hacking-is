# Beginner PicoMIni2022
## Objetivo
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/16/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level2.flag.txt.enc) in the same directory too.
## Pistas

Does that encoding look familiar?

## Solucion
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $ls
Addadshashanammu      code.py       Desktop     fixme1.py  Imágenes             level2.flag.txt.enc  Música   runme.py                  static.ltdis.x86_64.txt  Vídeos
Addadshashanammu.zip  convertme.py  Documentos  fixme2.py  level1.flag.txt.enc  level2.py            Notas    static                    strings                  warm
codebook.txt          Descargas     file        flag       level1.py            ltdis.sh             Público  static.ltdis.strings.txt  Templates
┌─[oscar@oscar-parrot]─[~]
└──╼ $nano level2.py
┌─[oscar@oscar-parrot]─[~]
└──╼ $python3.9
Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii(chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36))
"'de76'"
>>> 
┌─[oscar@oscar-parrot]─[~]
└──╼ $python3 level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
┌─[oscar@oscar-parrot]─[~]
└──╼ $

## Notas adicionales
## Referencias