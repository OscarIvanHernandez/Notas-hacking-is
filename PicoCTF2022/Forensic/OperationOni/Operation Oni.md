# PicoCTF2022 Forensic
## Objetivo
Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

-   [Download disk image](https://artifacts.picoctf.net/c/373/disk.img.gz)
-   Remote machine: `ssh -i key_file -p 59688 ctf-player@saturn.picoctf.net`
## Pistas
## Solucion
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $ls
disk.img.gz
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $gzip -d disk.img.gz 
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $ls
disk.img
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $man fls
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $fls -o 206848 disk.img 
d/d 458:	home
d/d 11:	lost+found
d/d 12:	boot
d/d 13:	etc
d/d 79:	proc
d/d 80:	dev
d/d 81:	tmp
d/d 82:	lib
d/d 85:	var
d/d 94:	usr
d/d 104:	bin
d/d 118:	sbin
d/d 464:	media
d/d 468:	mnt
d/d 469:	opt
d/d 470:	root
d/d 471:	run
d/d 473:	srv
d/d 474:	sys
V/V 33049:	$OrphanFiles
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $fls -o 206848 disk.img 470
r/r 2344:	.ash_history
d/d 3916:	.ssh
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $fls -o 206848 disk.img 3916
r/r 2345:	id_ed25519
r/r 2346:	id_ed25519.pub
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $man icat 
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $icat -o 206848 disk.img 2345
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $icat -o 206848 disk.img 2345 > key_file 
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $ls
disk.img  key_file
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $cat key_file 
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $chmod 400 key_file 
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $ls - la
ls: no se puede acceder a '-': No existe el fichero o el directorio
ls: no se puede acceder a 'la': No existe el fichero o el directorio
┌─[✗]─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $ls -la
total 235524
drwxr-xr-x 1 oscar oscar        32 oct 21 11:50 .
drwxr-xr-x 1 oscar oscar        50 oct 21 11:38 ..
-rw-r--r-- 1 oscar oscar 241172480 mar 15  2022 disk.img
-r-------- 1 oscar oscar       411 oct 21 11:50 key_file
┌─[oscar@oscar-parrot]─[~/forensic/2022/OperationOni]
└──╼ $ssh -i key_file -p 59688 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:59688 ([18.217.86.78]:59688)' can't be established.
ECDSA key fingerprint is SHA256:0L/+wJ14/Sk4s6Ue+TxXnAW7qNBuaMeIxA9dXp2zzaU.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:59688,[18.217.86.78]:59688' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.13.0-1025-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt 
picoCTF{k3y_5l3u7h_b5066e83}

## Notas adicionales

 fls lists the files and directory names in the image and can display file names of recently deleted files for the directory using the given inode.  If the inode argument is not
given, the inode value for the root directory is used. For example, on an NTFS file system it would be 5 and on a Ext3 file system it would be 2.


icat opens the named image(s) and copies the file with the specified inode number to standard output.


## Referencias
https://www.sleuthkit.org/autopsy/
https://www.youtube.com/watch?v=PVeV-S3Zbqk&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=32