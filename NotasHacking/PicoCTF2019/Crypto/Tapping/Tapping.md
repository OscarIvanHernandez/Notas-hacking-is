# PicoCTF2019 Crypto
## Objetivo

Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 48247`.

## Pistas
What kind of encoding uses dashes and dots?
## Solucion

┌─[oscar@oscar-parrot]─[~/crypto/2019/Tapping]
└──╼ $nc jupiter.challenges.picoctf.org 48247
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. .---- ..--- -.... .---- ....- ...-- ---.. .---- ---.. .---- } 
┌─[oscar@oscar-parrot]─[~/crypto/2019/Tapping]
└──╼ $

1)
Usando CyberChef, se decodifica por Morse 
	captura

picoCTF{M0RS3C0D31SFUN1261438181}

## Notas adicionales
## Referencias 
https://www.google.com/search?q=encoding+uses+dashes+and+dots&client=firefox-b-d&ei=K2FcY7HMAvXbkPIP6IKyiAU&ved=0ahUKEwjxjazNhYT7AhX1LUQIHWiBDFEQ4dUDCA4&uact=5&oq=encoding+uses+dashes+and+dots&gs_lcp=Cgxnd3Mtd2l6LXNlcnAQAzIGCAAQFhAeSgQITRgBSgQIQRgBSgQIRhgAUI8FWI8FYIgIaAFwAHgAgAF5iAF5kgEDMC4xmAEAoAECoAEBwAEB&sclient=gws-wiz-serp

https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=LS0gLS0tLS0gLi0uIC4uLiAuLi4tLSAtLi0uIC0tLS0tIC0uLiAuLi4tLSAuLS0tLSAuLi4gLi4tLiAuLi0gLS4gLi0tLS0gLi4tLS0gLS4uLi4gLi0tLS0gLi4uLi0gLi4uLS0gLS0tLi4gLi0tLS0gLS0tLi4gLi0tLS0g


