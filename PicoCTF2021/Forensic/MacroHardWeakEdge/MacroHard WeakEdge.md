# PicoCTF2022 Forensic
## Objetivo
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/3944a59474f9f676942282c50b9c3675/Forensics is fun.pptm)
## Pistas
## Solucion
┌─[oscar@oscar-parrot]─[~/forensic/macrohard]
└──╼ $ls -la
total 100
drwxr-xr-x 1 oscar oscar     42 oct 11 08:48  .
drwxr-xr-x 1 oscar oscar     18 oct 11 08:45  ..
-rw-r--r-- 1 oscar oscar 100093 mar 23  2021 'Forensics is fun.pptm'
┌─[oscar@oscar-parrot]─[~/forensic/macrohard]
└──╼ $unzip Forensics\ is\ fun.pptm 

...

┌─[oscar@oscar-parrot]─[~/forensic/macrohard]
└──╼ $cd ppt/slideMasters/
┌─[oscar@oscar-parrot]─[~/forensic/macrohard/ppt/slideMasters]
└──╼ $ls
hidden  _rels  slideMaster1.xml
┌─[oscar@oscar-parrot]─[~/forensic/macrohard/ppt/slideMasters]
└──╼ $cat hidden 
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q┌─[oscar@oscar-parrot]─[~/forensic/macrohard/ppt/slideMasters]
└──╼ $cat hidden | tr -d ' '
ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQ┌─[oscar@oscar-parrot]─[~/forensic/macrohard/ppt/slideMasters]
└──╼ $cat hidden | tr -d ' ' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: entrada inválida
┌─[✗]─[oscar@oscar-parrot]─[~/forensic/macrohard/ppt/slideMasters]
└──╼ $

## Notas adicionales
## Referencias
