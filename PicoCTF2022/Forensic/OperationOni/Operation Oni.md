# PicoCTF2022 Forensic
## Objetivo
Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

-   [Download disk image](https://artifacts.picoctf.net/c/373/disk.img.gz)
-   Remote machine: `ssh -i key_file -p 59688 ctf-player@saturn.picoctf.net`
## Pistas
## Solucion
## Notas adicionales

 fls lists the files and directory names in the image and can display file names of recently deleted files for the directory using the given inode.  If the inode argument is not
given, the inode value for the root directory is used. For example, on an NTFS file system it would be 5 and on a Ext3 file system it would be 2.


icat opens the named image(s) and copies the file with the specified inode number to standard output.


## Referencias
https://www.sleuthkit.org/autopsy/
https://www.youtube.com/watch?v=PVeV-S3Zbqk&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=32