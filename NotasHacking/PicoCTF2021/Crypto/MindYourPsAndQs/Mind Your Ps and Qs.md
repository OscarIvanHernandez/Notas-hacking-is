# PicoCTF2021 Crypto
## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values)

## Pistas
Bits are expensive, I used only a little bit over 100 to save money
## Solucion

┌─[oscar@oscar-parrot]─[~/crypto/2021/MindYourPsAndQs]
└──╼ $ls
values
┌─[oscar@oscar-parrot]─[~/crypto/2021/MindYourPsAndQs]
└──╼ $file values 
values: ASCII text
┌─[oscar@oscar-parrot]─[~/crypto/2021/MindYourPsAndQs]
└──╼ $cat values 
Decrypt my super sick RSA:
c: 843044897663847841476319711639772861390329326681532977209935413827620909782846667
n: 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
e: 65537
┌─[oscar@oscar-parrot]─[~/crypto/2021/MindYourPsAndQs]
└──╼ $

┌─[oscar@oscar-parrot]─[~/crypto/2021/MindYourPsAndQs]
└──╼ $python
Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c =843044897663847841476319711639772861390329326681532977209935413827620909782846667
>>> n = 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
>>> e = 65537
>>> p = 2159947535959146091116171018558446546179
>>> q = 658558036833541874645521278345168572231473
>>> 
>>> n = p*q
>>> n
1422450808944701344261903748621562998784243662042303391362692043823716783771691667
>>> tn = (p-1)*(q-1)
>>> d = inverse(e,tn)
>>> m = pow(c,d,n)
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_00264570}'
>>> 

## Notas adicionales
c - texto cifrado
m - mensaje texto plano
p - primo 1
q - primo 2
n - modulo
tn - totient n (euler)
e - exponente (llave publica) 2^16+1=65537
d - llave privada

n = p * q
tn = (p-1) * (q-1)
d = e mod inv tn / inverse(e,tn)

Encriptar          : c = m^e mod n       / pow(m,e,n)
Desencriptar    : m = c^d mod n       / pow(c,d,n)s



Se hace uso de una herramienta web para factorizar el valor de n 

## Referencias 
https://www.youtube.com/watch?v=pwGSp_4YHTg&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=44

http://factordb.com/index.php?query=1422450808944701344261903748621562998784243662042303391362692043823716783771691667
