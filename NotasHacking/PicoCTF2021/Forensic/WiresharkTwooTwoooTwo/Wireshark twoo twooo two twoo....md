# PicoCTF2022 Forensic
## Objetivo
Can you find the flag? [shark2.pcapng](https://mercury.picoctf.net/static/75300327ce3b9f252e9b8911997c8b0a/shark2.pcapng).
## Pistas
Did you really find _the_ flag?
Look for traffic that seems suspicious.
## Solucion

1)
Al aplicar un filtro dns en wireshark
Parece que haya una cadena en base64 en los primeros paquetes
	captura1
2)
Se aplica un filtro mas, ahora teniendo como parametro a la IP 18.217.1.57
	captura2
3)
Se aplica un nuevo filtro para ignorar los paquetes duplicados, donde filtraremos desde el query name contenga local
	captura3
4)
Se exportan los paquetes como CSV
	captura4
	captura4_2

┌─[oscar@oscar-parrot]─[~/forensic/2021/WhireSharkTwooTwooTwo]
└──╼ $cat data.csv 
"No.","Time","Source","Destination","Protocol","Length","Info"
"1637","9.440363","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x1dd2 A cGljb0NU.reddshrimpandherring.com.windomain.local"
"2046","11.972605","192.168.38.104","18.217.1.57","DNS","109","Standard query 0xabb9 A RntkbnNf.reddshrimpandherring.com.windomain.local"
"2448","14.605726","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x9e21 A M3hmMWxf.reddshrimpandherring.com.windomain.local"
"3153","16.506492","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x2ee1 A ZnR3X2Rl.reddshrimpandherring.com.windomain.local"
"3442","18.340155","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x2a4b A YWRiZWVm.reddshrimpandherring.com.windomain.local"
"3982","20.369626","192.168.38.104","18.217.1.57","DNS","105","Standard query 0x4068 A fQ==.reddshrimpandherring.com.windomain.local"
"4374","22.583745","192.168.38.104","18.217.1.57","DNS","105","Standard query 0x7418 A fQ==.reddshrimpandherring.com.windomain.local"
┌─[oscar@oscar-parrot]─[~/forensic/2021/WhireSharkTwooTwooTwo]
└──╼ $nano data.csv
*Se eliminan las lineas marcadas en captura5*

┌─[oscar@oscar-parrot]─[~/forensic/2021/WhireSharkTwooTwooTwo]
└──╼ $cat data.csv | cut -d ' ' -f 5

cGljb0NU.reddshrimpandherring.com.windomain.local"
RntkbnNf.reddshrimpandherring.com.windomain.local"
M3hmMWxf.reddshrimpandherring.com.windomain.local"
ZnR3X2Rl.reddshrimpandherring.com.windomain.local"
YWRiZWVm.reddshrimpandherring.com.windomain.local"
fQ==.reddshrimpandherring.com.windomain.local"

┌─[oscar@oscar-parrot]─[~/forensic/2021/WhireSharkTwooTwooTwo]
└──╼ $cat data.csv | cut -d ' ' -f 5 | cut -d '.' -f1

cGljb0NU
RntkbnNf
M3hmMWxf
ZnR3X2Rl
YWRiZWVm
fQ==

┌─[oscar@oscar-parrot]─[~/forensic/2021/WhireSharkTwooTwooTwo]
└──╼ $cat data.csv | cut -d ' ' -f 5 | cut -d '.' -f1 | tr -d '\n' 
cGljb0NURntkbnNfM3hmMWxfZnR3X2RlYWRiZWVmfQ==
┌─[oscar@oscar-parrot]─[~/forensic/2021/WhireSharkTwooTwooTwo]
└──╼ $cat data.csv | cut -d ' ' -f 5 | cut -d '.' -f1 | tr -d '\n' | base64 -d
picoCTF{dns_3xf1l_ftw_deadbeef}
┌─[oscar@oscar-parrot]─[~/forensic/2021/WhireSharkTwooTwooTwo]
└──╼ $



## Notas adicionales

Es sospechoso que haya tantas peticiones DNS

DNS exfiltration
https://www.google.com/search?client=firefox-b-d&q=DNS+exfiltration




## Referencias
