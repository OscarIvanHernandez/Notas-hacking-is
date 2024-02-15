# PicoCTF2022 Forensic
## Objetivo

Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/199/network-dump.flag.pcap)
## Pistas
## Solucion

┌─[oscar@oscar-parrot]─[~/forensic/2022/PacketsPrimer]
└──╼ $ls
network-dump.flag.pcap
┌─[oscar@oscar-parrot]─[~/forensic/2022/PacketsPrimer]
└──╼ $wireshark network-dump.flag.pcap 

1)
Se sigue el flujo de datos TCP y se encuentra
	p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ c e c c a a 7 f }

	captura


picoCTF{p4ck37_5h4rk_ceccaa7f}

## Notas adicionales
## Referencias
