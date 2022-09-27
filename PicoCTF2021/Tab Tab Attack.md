# PicoCTF2021
## Objetivo
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/e38f6a5b69b45d21e33cf7281d8c2531/Addadshashanammu.zip)


## Pistas
After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Solucion
┌─[oscar@oscar-parrot]─[~]
└──╼ $unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
┌─[oscar@oscar-parrot]─[~]
└──╼ $cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
┌─[oscar@oscar-parrot]─[~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└──╼ $ls -la
total 12
drwxr-xr-x 1 oscar oscar   42 mar 15  2021 .
drwxr-xr-x 1 oscar oscar   26 mar 15  2021 ..
-rwxr-xr-x 1 oscar oscar 8320 mar 15  2021 fang-of-haynekhtnamet
┌─[oscar@oscar-parrot]─[~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└──╼ $./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_f3553887}
┌─[oscar@oscar-parrot]─[~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└──╼ $

## Notas adicionales
## Referencias