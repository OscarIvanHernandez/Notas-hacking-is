# PicoCTF2022 Forensic
## Objetivo
Figure out how they moved the [flag](https://mercury.picoctf.net/static/cc6074838ede2edf9f805fd2b58bdc58/tftp.pcapng).
## Pistas
What are some other ways to hide data?
## Solucion
─[oscar@oscar-parrot]─[~/forensic]
└──╼ $mkdir trivial_flag_transfer_protocol
┌─[oscar@oscar-parrot]─[~/forensic]
└──╼ $cd trivial_flag_transfer_protocol/
┌─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $wget https://mercury.picoctf.net/static/cc6074838ede2edf9f805fd2b58bdc58/tftp.pcapng 

...

┌─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $wireshark tftp.pcapng 

ls
┌─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $
┌─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $ls
instructions.txt  picture1.bmp  picture2.bmp  picture3.bmp  plan  program.deb  tftp.pcapng
┌─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $cat instructions.txt 
GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA
┌─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $cat instructions.txt | base64
R1NHQ1FCUkZBR1JBUEVMQ0dCSEVHRU5TU1ZQRkJKUlpIRkdRVkZUSFZGUkJIRVNZTlRHRU5BRlNS
RS5TVlRIRVJCSEdOSk5MR0JVVlFSR1VSU1lOVE5BUVZKVllZUFVSUFhPTlBYU0JFR1VSQ1lOQQo=
┌─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $cat instructions.txt | base64 -d
!�@Ed@<B��CRIS��YQ�TT�TTAD�51�4RDbase64: entrada inválida
┌─[✗]─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $cat instructions.txt | tr [A-Z] [N-ZA-M]
TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN
┌─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $cat plan | tr [A-Z] [N-ZA-M]
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS
┌─[oscar@oscar-parrot]─[~/forensic/trivial_flag_transfer_protocol]
└──╼ $ls
instructions.txt  picture1.bmp  picture2.bmp  picture3.bmp  plan  program.deb  tftp.pcapng
┌─[oscar@oscar-parrot]─[~/forensic/2021/trivial_flag_transfer_protocol]
└──╼ $dpkg -I program.deb 
 paquete Debian nuevo, versión 2.0.
 tamaño 138310 bytes: archivo de control= 1250 bytes.
     826 bytes,    18 líneas     control              
    1184 bytes,    17 líneas     md5sums              
 Package: steghide
 Source: steghide (0.5.1-9.1)
 Version: 0.5.1-9.1+b1
 Architecture: amd64
 Maintainer: Ola Lundqvist <opal@debian.org>
 Installed-Size: 426
 Depends: libc6 (>= 2.2.5), libgcc1 (>= 1:4.1.1), libjpeg62-turbo (>= 1:1.3.1), libmcrypt4, libmhash2, libstdc++6 (>= 4.9), zlib1g (>= 1:1.1.4)
 Section: misc
 Priority: optional
 Description: A steganography hiding tool
  Steghide is steganography program which hides bits of a data file
  in some of the least significant bits of another file in such a way
  that the existence of the data file is not visible and cannot be proven.
  .
  Steghide is designed to be portable and configurable and features hiding
  data in bmp, wav and au files, blowfish encryption, MD5 hashing of
  passphrases to blowfish keys, and pseudo-random distribution of hidden bits
  in the container data.
┌─[oscar@oscar-parrot]─[~/forensic/2021/trivial_flag_transfer_protocol]
└──╼ $sudo dpkg -i program.deb 
[sudo] password for oscar: 
(Leyendo la base de datos ... 437129 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar program.deb ...
Desempaquetando steghide (0.5.1-9.1+b1) sobre (0.5.1-9.1+b1) ...
Configurando steghide (0.5.1-9.1+b1) ...
Procesando disparadores para man-db (2.10.1-1~bpo11+1) ...
┌─[oscar@oscar-parrot]─[~/forensic/2021/trivial_flag_transfer_protocol]
└──╼ $steghide --extract -sf picture1.bmp -p DUEDILIGENCE
steghide: �no pude extraer ning�n dato con ese salvoconducto!
┌─[✗]─[oscar@oscar-parrot]─[~/forensic/2021/trivial_flag_transfer_protocol]
└──╼ $steghide --extract -sf picture2.bmp -p DUEDILIGENCE
steghide: �no pude extraer ning�n dato con ese salvoconducto!
┌─[✗]─[oscar@oscar-parrot]─[~/forensic/2021/trivial_flag_transfer_protocol]
└──╼ $steghide --extract -sf picture3.bmp -p DUEDILIGENCE
anot� los datos extra�dos e/"flag.txt".
┌─[oscar@oscar-parrot]─[~/forensic/2021/trivial_flag_transfer_protocol]
└──╼ $ls
flag.txt  instructions.txt  picture1.bmp  picture2.bmp  picture3.bmp  plan  program.deb  tftp.pcapng
┌─[oscar@oscar-parrot]─[~/forensic/2021/trivial_flag_transfer_protocol]
└──╼ $cat flag.txt 
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
┌─[oscar@oscar-parrot]─[~/forensic/2021/trivial_flag_transfer_protocol]
└──╼ $


## Notas adicionales
instructions.txt esta rotado en rot13
## Referencias
https://www.youtube.com/watch?v=a15H2WXm5-8&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=29
