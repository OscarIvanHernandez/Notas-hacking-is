# PicoCTF2019 Forensic
## Objetivo

There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

## Pistas
There is data encoded somewhere... there might be an online decoder.

## Solucion
┌─[oscar@oscar-parrot]─[~/forensic_2019/WhatLiesWhitin]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png 


...

┌─[oscar@oscar-parrot]─[~/forensic_2019/WhatLiesWhitin]
└──╼ $file buildings.png 
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced
┌─[oscar@oscar-parrot]─[~/forensic_2019/WhatLiesWhitin]
└──╼ $open buildings.png 
┌─[✗]─[oscar@oscar-parrot]─[~/forensic_2019/WhatLiesWhitin]
└──╼ $sudo gem install zsteg

...

┌─[oscar@oscar-parrot]─[~/forensic_2019/WhatLiesWhitin]
└──╼ $zsteg buildings.png | grep picoCTF
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
┌─[oscar@oscar-parrot]─[~/forensic_2019/WhatLiesWhitin]
└──╼ $



## Notas adicionales
## Referencias
https://www.youtube.com/watch?v=bFUB-USG3sw&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=18