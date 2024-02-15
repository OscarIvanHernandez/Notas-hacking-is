# Pico CTF2019 Web
## Objetivo
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864
## Pistas
What is that cookie?
Have you heard of JWT?
## Solucion
1)
Usando la herramienta Coockie Editor, desplegamos el jwt y se copia el valor
2)
Se utiliza el debugger de jwt.io 
3)
Al pegar el contenido y el debugger muestre el contenido, se modifica el valor de user a admin
4)
Se pega el token que se genera al modificar el user en el jwt de la pagina 
5)
Aparece un Internal Server Error, se borra la Cookie jwt y se recarga la pagina 
6)
Se copia el contenido de la Cookie jwt
┌─[oscar@oscar-parrot]─[~]
└──╼ $nano hash
┌─[oscar@oscar-parrot]─[~]
└──╼ $cat hash 
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiQW55In0.lC458wuyJ9YVquBADtQ06HVKn0mLVZ10SW25EU7n628
┌─[oscar@oscar-parrot]─[~]
└──╼ $
7)
┌─[oscar@oscar-parrot]─[~]
└──╼ $ls /usr/share/wordlists/
dirb       dnsmap.txt     fern-wifi   nmap.lst        wfuzz
dirbuster  fasttrack.txt  metasploit  rockyou.txt.gz
┌─[oscar@oscar-parrot]─[~]
└──╼ $gzip -d /usr/share/wordlists/rockyou.txt.gz 
gzip: /usr/share/wordlists/rockyou.txt: Permission denied
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $sudo gzip -d /usr/share/wordlists/rockyou.txt.gz 
[sudo] password for oscar: 
	┌─[oscar@oscar-parrot]─[~]
└──╼ $ 
8)
	┌─[oscar@oscar-parrot]─[~]
└──╼ $ john hash -w- /usr/share/wordlists/rockyou.txt
...
ilovepico

9)
Se ingresa ilovepico en el debugger de jwt en el apartado "your-256-bit-secret"
y se copia el toquen generado
10)
Se pega el toquen en el jwt de la pagina, se guarda la Coockie y se recarga la pagina 

picoCTF{jawt_was_just_what_you_thought_1ca14548}



## Notas Adicionales

#### What is the JSON Web Token structure?

In its compact form, JSON Web Tokens consist of three parts separated by dots (`.`), which are:

-   Header
-   Payload
-   Signature

Therefore, a JWT typically looks like the following.

`xxxxx.yyyyy.zzzzz`

## Referencias
https://jwt.io/introduction
https://jwt.io/#debugger-io
https://www.youtube.com/watch?v=iaKbvrbcSko&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=10