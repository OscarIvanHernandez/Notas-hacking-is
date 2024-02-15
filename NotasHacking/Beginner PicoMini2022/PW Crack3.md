# Beginner PicoMIni2022
## Objetivo
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/25/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/25/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/25/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Pistas
There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solucion

┌─[oscar@oscar-parrot]─[~]
└──╼ $nano level3.py 
**
The strings below are 7 possibilities for the correct password. 
 (Only 1 is correct)
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]
**
┌─[oscar@oscar-parrot]─[~]
└──╼ $python3 level3.py 
Please enter correct password for flag: d3ab
That password is incorrect
┌─[oscar@oscar-parrot]─[~]
└──╼ $python3 level3.py 
Please enter correct password for flag: 1ea2
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_6f98a49f}
┌─[oscar@oscar-parrot]─[~]
└──╼ $


## Notas adicionales
## Referencias