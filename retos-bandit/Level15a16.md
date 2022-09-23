# Bandit level 15  → Level 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
 
## Solucion
bandit15@bandit:~$ openssl s_client -connect localhost:30001
...
---
read R BLOCK
	jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$



## Notas adicionales

## Referencias

