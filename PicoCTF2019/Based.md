# PICOCTF2019

## Descripcion
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

## Pistas
It might help to have multiple windows open.

## Solucion
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
street
Please give the 01110011 01110100 01110010 01100101 01100101 01110100 as a word.
...
you have 45 seconds.....

Input:
street
Please give me the  146 141 154 143 157 156 as a word.
Input:
falcon
Please give me the 636f6c6f7261646f as a word.
Input:
colorado
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}
┌─[oscar@oscar-parrot]─[~]
└──╼ $





## Notas adicionales
Haciendo uso de una herramienta externa, se realizan las diferentes conversiones de las bases que otorga el servidor

## Referencias
https://cyberchef.org