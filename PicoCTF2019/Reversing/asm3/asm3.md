# PicoCTF2019 Reversing
## Objetivo
What does asm3(0xba6c5a02,0xd101e3dd,0xbb86a173) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S)
## Pistas
more(?) [registers](https://wiki.skullsecurity.org/index.php?title=Registers)
## Solucion

Usando un emulador online se añade el proceso para llamar a la funcion con sus tres valores y se sigue el proceso con los rgistros 

	captura

Flag = 0x669b

## Notas adicionales
## Referencias 
https://www.youtube.com/watch?v=REQOuLONQQc

https://carlosrafaelgn.com.br/Asm86/