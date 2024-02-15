# PicoCTF2021 Crypto
## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png)
## Pistas
[https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)

Think of different ways you can "stack" images

## Solucion

┌─[oscar@oscar-parrot]─[~/crypto/2021/Pixelated]
└──╼ $java -jar /opt/stegsolve.jar 

1)
Se abre la pimera imagen 
	captura
2)
Se realiza una combinacion con la segunda imagen
	captua2
3)
Se recorren las direferentes condiciones hasta llegar al ADD
	caputra3

picoCTF{7188864c}




## Notas adicionales
https://github.com/zardus/ctf-tools/blob/master/stegsolve/install

## Referencias 
https://www.youtube.com/watch?v=zWU6MV8dQQ4&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=43
