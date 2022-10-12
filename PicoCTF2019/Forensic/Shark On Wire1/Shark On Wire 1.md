# PicoCTF2019 Forensic
## Objetivo

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Pistas
Try using a tool like Wireshark
What are streams?

## Solucion
┌─[oscar@oscar-parrot]─[~/forensic_2019]
└──╼ $mkdir SharkOnWire1
┌─[oscar@oscar-parrot]─[~/forensic_2019]
└──╼ $cd SharkOnWire1/
┌─[oscar@oscar-parrot]─[~/forensic_2019/SharkOnWire1]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap 

...

┌─[✗]─[oscar@oscar-parrot]─[~/forensic_2019/SharkOnWire1]
└──╼ $wireshark capture.pcap 

...

Ubicando algun paquete UDP y siguiendo con flujo de datos se puede encontrar..

picoCTF{StaT31355_636f6e6e}

## Notas adicionales
## Referencias
https://www.youtube.com/watch?v=Govu_p-wf4I&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=15 
