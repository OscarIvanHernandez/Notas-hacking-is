# PicoCTF2021
## Objetivo
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 22342`, but it doesn't speak English...

## Pistas
## Solucion
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $nc mercury.picoctf.net 22342
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
53 
102 
98 
53 
101 
53 
49 
100 
125 
10 
┌─[oscar@oscar-parrot]─[~]
└──╼ 

picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5e51d}

## Notas adicionales

Hay que traducir el codigo que se nos otorga, este se encuentra cifrado en decimal

## Referencias
https://github.com/ZeroDayTea/PicoCTF-2021-Killer-Queen-Writeups/blob/main/GeneralSkills/NiceNetcat.md

https://cyberchef.org/#recipe=From_Decimal('Space',false)&input=MTEyIAoxMDUgCjk5IAoxMTEgCjY3IAo4NCAKNzAgCjEyMyAKMTAzIAo0OCAKNDggCjEwMCAKOTUgCjEwNyAKNDkgCjExNiAKMTE2IAoxMjEgCjMzIAo5NSAKMTEwIAo0OSAKOTkgCjUxIAo5NSAKMTA3IAo0OSAKMTE2IAoxMTYgCjEyMSAKMzMgCjk1IAo1MyAKMTAyIAo5OCAKNTMgCjEwMSAKNTMgCjQ5IAoxMDAgCjEyNSAKMTAK