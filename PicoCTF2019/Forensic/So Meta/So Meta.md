# PicoCTF2019 Forensic
## Objetivo
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).
## Pistas
What does meta mean in the context of files?
Ever heard of metadata?
## Solucion
┌─[oscar@oscar-parrot]─[~/forensic_2019]
└──╼ $mkdir SoMeta
┌─[oscar@oscar-parrot]─[~/forensic_2019]
└──╼ $cd SoMeta/
┌─[oscar@oscar-parrot]─[~/forensic_2019/SoMeta]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png 

┌─[oscar@oscar-parrot]─[~/forensic_2019/SoMeta]
└──╼ $ls
pico_img.png
┌─[oscar@oscar-parrot]─[~/forensic_2019/SoMeta]
└──╼ $exiftool pico_img.png 
ExifTool Version Number         : 12.16
File Name                       : pico_img.png
Directory                       : .
File Size                       : 106 KiB
File Modification Date/Time     : 2020:10:26 12:38:23-06:00
File Access Date/Time           : 2022:10:11 18:47:19-05:00
File Inode Change Date/Time     : 2022:10:11 18:47:19-05:00
File Permissions                : rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_d8944929}
Image Size                      : 600x600
Megapixels                      : 0.360
┌─[oscar@oscar-parrot]─[~/forensic_2019/SoMeta]
└──╼ $



## Notas adicionales
exiftool lee y escribe meta en formacion en archivos

## Referencias
https://www.youtube.com/watch?v=Govu_p-wf4I&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=15
