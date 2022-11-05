# PicoCTF2022 Crypto
## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/393/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Pistas
Do you know what `mod 37` means?

`mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solucion
┌─[oscar@oscar-parrot]─[~/crypto/2022/Basic_mod1]
└──╼ $cat message.txt 
54 396 131 198 225 258 87 258 128 211 57 235 114 258 144 220 39 175 330 338 297 288 
┌─[oscar@oscar-parrot]─[~/crypto/2022/Basic_mod1]
└──╼ $
┌─[✗]─[oscar@oscar-parrot]─[~/crypto/2022/Basic_mod1]
└──╼ $nano exp.py
	captura
┌─[oscar@oscar-parrot]─[~/crypto/2022/Basic_mod1]
└──╼ $

┌─[✗]─[oscar@oscar-parrot]─[~/crypto/2022/Basic_mod1]
└──╼ $python exp.py 
picoCTF{R0UND_N_R0UND_79C18FB3}
┌─[oscar@oscar-parrot]─[~/crypto/2022/Basic_mod1]
└──╼ $

## Notas adicionales
## Referencias 
https://www.youtube.com/watch?v=t3vRV-j0mF0&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=46
