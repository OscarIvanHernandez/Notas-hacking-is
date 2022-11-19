# PicoCTF2019 Reversing
## Objetivo
This vault uses an XOR encryption scheme. The source code for this vault is here: [VaultDoor6.java](https://jupiter.challenges.picoctf.org/static/86e94cc555b2ca7375424c884ef581a6/VaultDoor6.java)
## Pistas
If X ^ Y = Z, then Z ^ Y = X. Write a program that decrypts the flag based on this fact.
## Solucion

┌─[oscar@oscar-parrot]─[~/reversing/2019/vault-door-6]
└──╼ $ls
VaultDoor6.java
┌─[oscar@oscar-parrot]─[~/reversing/2019/vault-door-6]
└──╼ $nano VaultDoor6.java 
┌─[oscar@oscar-parrot]─[~/reversing/2019/vault-door-6]
└──╼ $

...

┌─[oscar@oscar-parrot]─[~/reversing/2019/vault-door-6]
└──╼ $python
Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> mybytes = [0x3b, 0x65, 0x21, 0xa , 0x38, 0x0 , 0x36, 0x1d,
...             0xa , 0x3d, 0x61, 0x27, 0x11, 0x66, 0x27, 0xa ,
...             0x21, 0x1d, 0x61, 0x3b, 0xa , 0x2d, 0x65, 0x27,
...             0xa , 0x66, 0x36, 0x30, 0x67, 0x6c, 0x64, 0x6c,
... ]
>>> mybytes
[59, 101, 33, 10, 56, 0, 54, 29, 10, 61, 97, 39, 17, 102, 39, 10, 33, 29, 97, 59, 10, 45, 101, 39, 10, 102, 54, 48, 103, 108, 100, 108]
>>> flag = [ i ^ 0x55 for i in mybytes]
>>> flag
[110, 48, 116, 95, 109, 85, 99, 72, 95, 104, 52, 114, 68, 51, 114, 95, 116, 72, 52, 110, 95, 120, 48, 114, 95, 51, 99, 101, 50, 57, 49, 57]
>>> flag = [chr(i) for i in flag]
>>> ''.join(flag)
'n0t_mUcH_h4rD3r_tH4n_x0r_3ce2919'
>>> 

picoCTF{n0t_mUcH_h4rD3r_tH4n_x0r_3ce2919}

## Notas adicionales
## Referencias 
