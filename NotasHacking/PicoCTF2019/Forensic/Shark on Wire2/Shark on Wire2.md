# PicoCTF2019 Forensic
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
## Pistas

## Solucion
1) 
Usando wireshark, se utiliza un filtro udp.dstport 22
	captura1
2)

Si al valor del puerto se le resta 5000, se obtiene un valor tipo character que se puede traducir en pyhton

┌─[✗]─[oscar@oscar-parrot]─[~/forensic/2019/SharkOnWire2]
└──╼ $python3.9
Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(112)
'p'
>>> chr(105)
'i'
>>> chr(099)
  File "<stdin>", line 1
    chr(099)
          ^
SyntaxError: leading zeros in decimal integer literals are not permitted; use an 0o prefix for octal integers
>>> chr(99)
'c'
>>

3)
┌─[oscar@oscar-parrot]─[~/forensic/2019/SharkOnWire2]
└──╼ $python3 -m pip install scapy
Requirement already satisfied: scapy in /usr/lib/python3/dist-packages (2.4.4)
┌─[oscar@oscar-parrot]─[~/forensic/2019/SharkOnWire2]
└──╼ $nano exp.py
from scapy.all import *

packets = rdpcap('capture.pcap')
flag = ''


for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)


print(flag)



┌─[oscar@oscar-parrot]─[~/forensic/2019/SharkOnWire2]
└──╼ $python3 exp.py 
picoCTF{p1LLf3r3d_data_v1a_st3g0}


## Notas adicionales
## Referencias

https://www.youtube.com/watch?v=WcMl1SvQ6hI&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=23