# PicoCTF2021
## Objetivo
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `481e7b14`

## Pistas
## Solucion
┌─[oscar@oscar-parrot]
└──╼ $ssh ctf-player@venus.picoctf.net -p 57707
The authenticity of host '[venus.picoctf.net]:57707 ([3.131.124.143]:57707)' can't be established.
ECDSA key fingerprint is SHA256:NrQkIxNEQQho/GA7jE0WlIa7Jh4VF9sAvC5awkbuj1Q.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[venus.picoctf.net]:57707,[3.131.124.143]:57707' (ECDSA) to the list of known hosts.
ctf-player@venus.picoctf.net's password: 
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

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

ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ ./instructions-to-20f3.txt
-bash: ./instructions-to-20f3.txt: No such file or directory
ctf-player@pico-chall$ ls -la
total 16
drwxr-xr-x 1 ctf-player ctf-player 4096 Mar 16  2021 .
drwxr-xr-x 1 ctf-player ctf-player 4096 Sep 26 23:40 ..
-rw-r--r-- 1 ctf-player ctf-player   14 Mar 16  2021 1of3.flag.txt
-rw-r--r-- 1 ctf-player ctf-player   56 Mar 16  2021 instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cd ./
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls -la
total 32
drwxr-xr-x 1 ctf-player ctf-player 4096 Sep 26 23:40 .
drwxr-xr-x 1 root       root       4096 Mar 16  2021 ..
drwx------ 2 ctf-player ctf-player 4096 Sep 26 23:40 .cache
-rw-r--r-- 1 ctf-player ctf-player   80 Mar 16  2021 .profile
drw------- 1 ctf-player ctf-player 4096 Mar 16  2021 .ssh
-rw-r--r-- 1 ctf-player ctf-player   10 Mar 16  2021 3of3.flag.txt
drwxr-xr-x 1 ctf-player ctf-player 4096 Mar 16  2021 drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt 
1118a9a4}
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls -la
total 16
drwxr-xr-x 1 root       root       4096 Mar 16  2021 .
drwxr-xr-x 1 root       root       4096 Sep 26 23:39 ..
drwxr-xr-x 1 ctf-player ctf-player 4096 Sep 26 23:40 ctf-player
ctf-player@pico-chall$ cat ctf-player/
cat: ctf-player/: Is a directory
ctf-player@pico-chall$ ^C
ctf-player@pico-chall$ cd ctf-player/
ctf-player@pico-chall$ ls -la
total 32
drwxr-xr-x 1 ctf-player ctf-player 4096 Sep 26 23:40 .
drwxr-xr-x 1 root       root       4096 Mar 16  2021 ..
drwx------ 2 ctf-player ctf-player 4096 Sep 26 23:40 .cache
-rw-r--r-- 1 ctf-player ctf-player   80 Mar 16  2021 .profile
drw------- 1 ctf-player ctf-player 4096 Mar 16  2021 .ssh
-rw-r--r-- 1 ctf-player ctf-player   10 Mar 16  2021 3of3.flag.txt
drwxr-xr-x 1 ctf-player ctf-player 4096 Mar 16  2021 drop-in
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls -la
total 16
drwxr-xr-x 1 root       root       4096 Mar 16  2021 .
drwxr-xr-x 1 root       root       4096 Sep 26 23:39 ..
drwxr-xr-x 1 ctf-player ctf-player 4096 Sep 26 23:40 ctf-player
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls -la
total 92
drwxr-xr-x   1 root root 4096 Sep 26 23:39 .
drwxr-xr-x   1 root root 4096 Sep 26 23:39 ..
-rwxr-xr-x   1 root root    0 Sep 26 23:39 .dockerenv
-rw-r--r--   1 root root   17 Mar 16  2021 2of3.flag.txt
drwxr-xr-x   1 root root 4096 Mar 16  2021 bin
drwxr-xr-x   2 root root 4096 Apr 24  2018 boot
drwxr-xr-x   5 root root  340 Sep 26 23:39 dev
drwxr-xr-x   1 root root 4096 Sep 26 23:39 etc
drwxr-xr-x   1 root root 4096 Mar 16  2021 home
-rw-r--r--   1 root root   51 Mar 16  2021 instructions-to-3of3.txt
drwxr-xr-x   1 root root 4096 Mar 16  2021 lib
drwxr-xr-x   2 root root 4096 Feb 22  2021 lib64
drwxr-xr-x   2 root root 4096 Feb 22  2021 media
drwxr-xr-x   2 root root 4096 Feb 22  2021 mnt
drwxr-xr-x   1 root root 4096 Mar 16  2021 opt
dr-xr-xr-x 178 root root    0 Sep 26 23:39 proc
drwx------   2 root root 4096 Feb 22  2021 root
drwxr-xr-x   1 root root 4096 Sep 26 23:40 run
drwxr-xr-x   1 root root 4096 Mar 16  2021 sbin
drwxr-xr-x   2 root root 4096 Feb 22  2021 srv
dr-xr-xr-x  13 root root    0 Sep 26 23:39 sys
drwxrwxrwt   1 root root 4096 Mar 16  2021 tmp
drwxr-xr-x   1 root root 4096 Feb 22  2021 usr
drwxr-xr-x   1 root root 4096 Feb 22  2021 var
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ 

## Notas adicionales
Se realiza una inspeccion por los directorios hasta encontrar las partes de la bandera
## Referencias