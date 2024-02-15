# PicoCTF2022 Forensic
## Objetivo
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/294/anthem.flag.txt).

## Pistas
Download the file and search for the flag based on the known prefix.
## Solucion
┌─[oscar@oscar-parrot]─[~/forensic/2022/LookeyHere]
└──╼ $cat anthem.flag.txt 
...
┌─[oscar@oscar-parrot]─[~/forensic/2022/LookeyHere]
└──╼ $cat anthem.flag.txt | grep pico
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}
┌─[oscar@oscar-parrot]─[~/forensic/2022/LookeyHere]

## Notas adicionales
## Referencias
