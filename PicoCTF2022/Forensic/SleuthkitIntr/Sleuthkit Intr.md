# PicoCTF2022 Forensic
## Objetivo
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

-   [Download diskhttps://artifacts.picoctf.net/c/114/disk.img.gz image](https://artifacts.picoctf.net/c/114/disk.img.gz)
-   Access checker program: `nc saturn.picoctf.net 52279`

## Pistas
## Solucion
┌─[oscar@oscar-parrot]─[~/forensic/2022/SleuthkitIntr]
└──╼ $file disk.img.gz 
disk.img.gz: gzip compressed data, was "disk.img", last modified: Tue Sep 21 19:34:53 2021, from Unix, original size modulo 2^32 104857600
┌─[oscar@oscar-parrot]─[~/forensic/2022/SleuthkitIntr]
└──╼ $gzip -d disk.img.gz 
┌─[oscar@oscar-parrot]─[~/forensic/2022/SleuthkitIntr]
└──╼ $ls
disk.img
┌─[✗]─[oscar@oscar-parrot]─[~/forensic/2022/SleuthkitIntr]
└──╼ $mmls -V
The Sleuth Kit ver 4.10.1
┌─[oscar@oscar-parrot]─[~/forensic/2022/SleuthkitIntr]
└──╼ $man mmls 
┌─[oscar@oscar-parrot]─[~/forensic/2022/SleuthkitIntr]
└──╼ $mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
┌─[oscar@oscar-parrot]─[~/forensic/2022/SleuthkitIntr]
└──╼ $nc saturn.picoctf.net 52279
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}
┌─[oscar@oscar-parrot]─[~/forensic/2022/SleuthkitIntr]
└──╼ $



## Notas adicionales

mmls  - Display the partition layout of a volume system 

## Referencias
https://www.sleuthkit.org/

