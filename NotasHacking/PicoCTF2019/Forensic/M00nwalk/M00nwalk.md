# PicoCTF2019 Forensic
## Objetivo
Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

## Pistas
How did pictures from the moon landing get sent back to Earth?

What is the CMU mascot?, that might help select a RX option

## Solucion

┌─[oscar@oscar-parrot]─[~/forensic_2019]
└──╼ $mkdir M00nwalk
┌─[oscar@oscar-parrot]─[~/forensic_2019]
└──╼ $cd M00nwalk/
┌─[oscar@oscar-parrot]─[~/forensic_2019/M00nwalk]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav 

...

┌─[oscar@oscar-parrot]─[~/forensic_2019/M00nwalk]
└──╼ $cd /opt
┌─[✗]─[oscar@oscar-parrot]─[/opt]
└──╼ $sudo git clone https://github.com/colaclanth/sstv.git
...

┌─[✗]─[oscar@oscar-parrot]─[/opt]
└──╼ $cd sstv/
┌─[oscar@oscar-parrot]─[/opt/sstv]
└──╼ $sudo python3 setup.py install

...

┌─[oscar@oscar-parrot]─[/]
└──╼ $cd home/oscar/forensic_2019/M00nwalk/
┌─[oscar@oscar-parrot]─[~/forensic_2019/M00nwalk]
└──╼ $ls
message.wav
┌─[oscar@oscar-parrot]─[~/forensic_2019/M00nwalk]
└──╼ $sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                                         [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
┌─[oscar@oscar-parrot]─[~/forensic_2019/M00nwalk]
└──╼ $

picoCTF{beep_boop_im_in_space}

## Notas adicionales
En forma de audio se puede codificar una imagen 
## Referencias
https://github.com/colaclanth/sstv
https://www.youtube.com/watch?v=UyLTEpAz6eE&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=19