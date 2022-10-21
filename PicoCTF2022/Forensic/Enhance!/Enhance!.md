# PicoCTF2022 Forensic
## Objetivo
Download this image file and find the flag.

-   [Download image file](https://artifacts.picoctf.net/c/136/drawing.flag.svg)

## Pistas

## Solucion

┌─[✗]─[oscar@oscar-parrot]─[~/forensic/2022/Enhance!]
└──╼ $strings  drawing.flag.svg | grep pico
┌─[✗]─[oscar@oscar-parrot]─[~/forensic/2022/Enhance!]
└──╼ $xxd drawing.flag.svg 
...

00000ea0: 3131 3134 3722 0a20 2020 2020 2020 2020  11147".         
00000eb0: 7374 796c 653d 2266 6f6e 742d 7369 7a65  style="font-size
00000ec0: 3a30 2e30 3033 3532 3738 3170 783b 6c69  :0.00352781px;li
00000ed0: 6e65 2d68 6569 6768 743a 312e 3235 3b66  ne-height:1.25;f
00000ee0: 696c 6c3a 2366 6666 6666 663b 7374 726f  ill:#ffffff;stro
00000ef0: 6b65 2d77 6964 7468 3a30 2e32 3634 3538  ke-width:0.26458
00000f00: 3333 323b 220a 2020 2020 2020 2020 2069  332;".         i
00000f10: 643d 2274 7370 616e 3337 3634 223e 4620  d="tspan3764">F 
00000f20: 7b20 3320 6e20 6820 3420 6e20 3c2f 7473  { 3 n h 4 n </ts
00000f30: 7061 6e3e 3c74 7370 616e 0a20 2020 2020  pan><tspan.     
00000f40: 2020 2020 736f 6469 706f 6469 3a72 6f6c      sodipodi:rol
00000f50: 653d 226c 696e 6522 0a20 2020 2020 2020  e="line".       
00000f60: 2020 783d 2231 3037 2e34 3330 3134 220a    x="107.43014".
00000f70: 2020 2020 2020 2020 2079 3d22 3133 322e           y="132.
00000f80: 3131 3538 3822 0a20 2020 2020 2020 2020  11588".         
00000f90: 7374 796c 653d 2266 6f6e 742d 7369 7a65  style="font-size
00000fa0: 3a30 2e30 3033 3532 3738 3170 783b 6c69  :0.00352781px;li
00000fb0: 6e65 2d68 6569 6768 743a 312e 3235 3b66  ne-height:1.25;f
00000fc0: 696c 6c3a 2366 6666 6666 663b 7374 726f  ill:#ffffff;stro
00000fd0: 6b65 2d77 6964 7468 3a30 2e32 3634 3538  ke-width:0.26458
00000fe0: 3333 323b 220a 2020 2020 2020 2020 2069  332;".         i
00000ff0: 643d 2274 7370 616e 3337 3532 223e 6320  d="tspan3752">c 
00001000: 3320 6420 5f20 6120 6120 6220 3720 3220  3 d _ a a b 7 2 
00001010: 3920 6420 6420 7d3c 2f74 7370 616e 3e3c  9 d d }</tspan><
00001020: 2f74 6578 743e 0a20 203c 2f67 3e0a 3c2f  /text>.  </g>.</
00001030: 7376 673e 0a                             svg>.


*Mostrando todos los datos hexadecimales, si se observa bien al final se pueden apreciar valores en diferentes partes, que inician con { 

00000f20: 7b20 3320 6e20 6820 3420 6e20 3c2f 7473  { 3 n h 4 n </ts

y otros valores que cierran en }

00000ff0: 643d 2274 7370 616e 3337 3532 223e 6320  d="tspan3752">c 
00001000: 3320 6420 5f20 6120 6120 6220 3720 3220  3 d _ a a b 7 2 
00001010: 3920 6420 6420 7d3c 2f74 7370 616e 3e3c  9 d d }

Juntando la cadena
{3nh4nc3d_aab729dd} 

picoCTF{3nh4nc3d_aab729dd} 



Tambien utilizando la herramineta pluma
	captura
Se puede explorar el contenido, y recorriendolo se puede encontrar lo siguiente 
	captura2

Donse se observa el formato completo de la bandera separada a lo largo del archivo


## Notas adicionales
## Referencias
