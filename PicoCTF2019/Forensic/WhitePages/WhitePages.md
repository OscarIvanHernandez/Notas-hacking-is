# PicoCTF2019 Inspector
## Objetivo
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt) is all blank!
## PIstas

## Solucion
┌─[oscar@oscar-parrot]─[~]
└──╼ $mkdir whitepages
┌─[oscar@oscar-parrot]─[~]
└──╼ $cd whitepages/
┌─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt 

...

┌─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $file whitepages.txt 
whitepages.txt: UTF-8 Unicode text, with very long lines, with no line terminators
┌─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $cat whitepages.txt 
...

┌─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $pyhton3 -m pip install pwntools
bash: pyhton3: orden no encontrada
┌─[✗]─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $python3 -m pip install pwntools
...
┌─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $nano exp.py
┌─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $python3.9 exp.py 
Traceback (most recent call last):
  File "/home/oscar/whitepages/exp.py", line 2, in <module>
    file = opne('whitepages.txt','rb')
NameError: name 'opne' is not defined
┌─[✗]─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $nano exp.py 
┌─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $python3.9 exp.py 
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}\n\t\t'
┌─[oscar@oscar-parrot]─[~/whitepages]
└──╼ $

## Notas adicionales
## Referencias