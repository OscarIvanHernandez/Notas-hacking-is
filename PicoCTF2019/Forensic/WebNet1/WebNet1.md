# PicoCTF2019 Forensic
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.
## Pistas
Try using a tool like Wireshark.
## Solucion
1)
Usando wireshark 
	captura1

┌─[oscar@oscar-parrot]─[~/forensic/2019/WebNet1]
└──╼ $ls
capture.pcap  picopico.key
┌─[oscar@oscar-parrot]─[~/forensic/2019/WebNet1]
└──╼ $wireshark capture.pcap &

2)
Usando la herramienta de edicion, se hubica preferencias,
se depliegan los protocolos, se busca el protocolo TLS y elimina si ya hay una key, se añade una nueva utilizando el picopico.key
	captura2



*En este caso, al realizar una busqueda entre los detalles o los bytes, no se encontrar nada*


3)
Buscando la herramineta de archivo, se utiliza la opcion de exportar objetos en el apartado HTPP, extrayendo la imagen que se encuentra ahí
	captura3
	caotura4
4)
┌─[oscar@oscar-parrot]─[~/forensic/2019/WebNet1]
└──╼ $strings vulture.jpg -n15
picoCTF{honey.roasted.peanuts}
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
┌─[oscar@oscar-parrot]─[~/forensic/2019/WebNet1]
└──╼ $

## Notas adicionales
## Referencias
https://www.youtube.com/watch?v=Ym3i79nEHjw&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=25