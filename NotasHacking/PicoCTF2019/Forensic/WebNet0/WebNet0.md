# PicoCTF2019 Forensic
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
## Pistas
Try using a tool like Wireshark.
How can you decrypt the TLS stream?
## Solucion
1)
Usando wireshark 
	captura1

┌─[oscar@oscar-parrot]─[~/forensic/2019/WebNet0]
└──╼ $ls
capture.pcap  picopico.key
┌─[oscar@oscar-parrot]─[~/forensic/2019/WebNet0]
└──╼ $wireshark capture.pcap &

2)
Usando la herramienta de edicion, se hubica preferencias 
	captura2

3)
Se depliegan los protocolos, se busca el protocolo TLS y se añade uno nuevo utilizando el picopico.key
	captura3

4)
Se realiza una busqueda en los detalles del paquete 

Pico-Flag: picoCTF{nongshim.shrimp.crackers}


## Notas adicionales
## Referencias
https://en.wikipedia.org/wiki/Transport_Layer_Security
https://www.youtube.com/watch?v=9uflLPoETOc&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=24