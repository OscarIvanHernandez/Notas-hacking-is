# PicoCTF2022 Crypto
## Objetivo
Morse code is well known. Can you decrypt this? Download the file [here](https://artifacts.picoctf.net/c/235/morse_chal.wav). Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.
## Pistas
Audacity is a really good program to analyze morse code audio.
## Solucion

1)
Usando una herramienta we, morse code audio decoder
se sube el audio y se empieza a decodificar
	captura
2)
Usando python se modifca el texto a minusculas y se da el formato que se pide 
┌─[✗]─[oscar@oscar-parrot]─[~/crypto/2022/morse-code]
└──╼ $python

Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
   
 W H 4 7 H 4 7 H 9 0 D W 2 0 U 9 H 7
  File "<stdin>", line 1
    W H 4 7 H 4 7 H 9 0 D W 2 0 U 9 H 7
      ^
SyntaxError: invalid syntax
"WH47 H47H 90D W20U9H7".lower().replace(' ','')
'wh47h47h90dw20u9h7'
"WH47 H47H 90D W20U9H7".lower().replace(' ','_')
'wh47_h47h_90d_w20u9h7'

picoCTF{wh47_h47h_90d_w20u9h7}

## Notas adicionales
## Referencias 

https://morsecode.world/international/decoder/audio-decoder-adaptive.html
