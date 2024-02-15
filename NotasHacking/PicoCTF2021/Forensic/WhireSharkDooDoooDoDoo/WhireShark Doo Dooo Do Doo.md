# PicoCTF2021 Forensic
## Objetivo
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/0505a462ac9beb7412596855df280f6b/shark1.pcapng).
## Pistas
## Solucion

┌─[oscar@oscar-parrot]─[~/forensic/2021/WhireSharkDooDoooDoDoo]
└──╼ $ls
shark1.pcapng
┌─[oscar@oscar-parrot]─[~/forensic/2021/WhireSharkDooDoooDoDoo]
└──╼ $wireshark shark1.pcapng 

1)
Empeze navengando entre los pquetes TCP 

2)
Recorriendo los paquetes hasta el numero 5, se puede observar...
	captura 

3)
Usando CyberChef, se decodifica en ROT13 y se obtiene
picoCTF{p33kab00_1_s33_u_deadbeef}

	captura2

## Notas Adicionales
## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=Y3ZwYlBHU3tjMzN4bm8wMF8xX2YzM19oX3FybnFvcnJzfQo
