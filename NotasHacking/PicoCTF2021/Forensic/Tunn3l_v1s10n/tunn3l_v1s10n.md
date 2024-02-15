# PicoCTF2022 Forensic
## Objetivo
We found this [file](https://mercury.picoctf.net/static/09a86202e72dbdb5bf4d1b5d2c6a5b86/tunn3l_v1s10n). Recover the flag.
## Pistas
Weird that it won't display right...
## Solucion
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $ls
tunn3l_v1s10n
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $file tunn3l_v1s10n 
tunn3l_v1s10n: data
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $xxd tunn3l_v1s10n | head
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/
00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v
00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT
00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $mv tunn3l_v1s10n tunn3l_v1s10n.bmp
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $hexedit tunn3l_v1s10n.bmp 

"
Usando el editor, se hubica la linea 
00000000   42 4D 8E 26  2C 00 00 00  00 00 BA D0  00 00 BA D0
y se corrige
00000000   42 4D 8E 26  2C 00 00 00  00 00 28 00  00 00 28 00
Para corregir el encabezado y corregir donde inician los datos
"
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $open tunn3l_v1s10n.bmp
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $exiftool tunn3l_v1s10n.bmp 
ExifTool Version Number         : 12.16
File Name                       : tunn3l_v1s10n.bmp
Directory                       : .
File Size                       : 2.8 MiB
File Modification Date/Time     : 2022:10:17 19:10:48-05:00
File Access Date/Time           : 2022:10:17 19:02:44-05:00
File Inode Change Date/Time     : 2022:10:17 19:10:48-05:00
File Permissions                : rw-r--r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Image Size                      : 1134x306
Megapixels                      : 0.347

*El alto de la imagen es muy pequeño considerando el tamaño de la imagen de 2.8 MiB*

┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $hexedit tunn3l_v1s10n.bmp 
"
Usando el editor se ubica la linea que se muestra en la captura y se remplaza el valor para incrementar el alto en la imagen
"
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $exiftool tunn3l_v1s10n.bmp 
ExifTool Version Number         : 12.16
File Name                       : tunn3l_v1s10n.bmp
Directory                       : .
File Size                       : 2.8 MiB
File Modification Date/Time     : 2022:10:17 19:24:07-05:00
File Access Date/Time           : 2022:10:17 19:02:44-05:00
File Inode Change Date/Time     : 2022:10:17 19:24:07-05:00
File Permissions                : rw-r--r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 1088
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Image Size                      : 1134x1088
Megapixels                      : 1.2
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $open tunn3l_v1s10n.bmp 
┌─[oscar@oscar-parrot]─[~/forensic/2021/Tunn3l_v1s10n]
└──╼ $

picoCTF{qu1t3_a_v13w_2020}


## Notas adicionales
## Referencias
https://en.wikipedia.org/wiki/BMP_file_format
https://www.youtube.com/watch?v=1ucy2G1PIh4&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=27
