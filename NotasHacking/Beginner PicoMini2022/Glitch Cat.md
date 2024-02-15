# Beginner PicoMIni2022
## Objetivo
Our flag printing service has started glitching! `$ nc saturn.picoctf.net 65353`

## Pistas
ASCII is one of the most common encodings used in programming

## Solucion
┌─[oscar@oscar-parrot]─[~]
└──╼ $nc saturn.picoctf.net 65353
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
┌─[oscar@oscar-parrot]─[~]
└──╼ $^C
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $python3.9
Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii(chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64))
"'9c42a45d'"
>>> 
KeyboardInterrupt
>>> 
┌─[oscar@oscar-parrot]─[~]
└──╼ $

picoCTF{gl17ch_m3_n07_9c42a45d'}
## Notas adicionales
## Referencias