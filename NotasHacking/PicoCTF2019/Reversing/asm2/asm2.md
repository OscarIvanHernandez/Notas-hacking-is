# PicoCTF2019 Reversing
## Objetivo
What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)
## Pistas
assembly [conditions](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)
## Solucion

Gracias a que los valores con los que se realiza este ejercicio genera un ciclo algo grande para llevar el proceso de forma manual, cree lo siguiente en python

local1 = 0x2e
local2 = 0xb

while(local2 <= 0x63f3):
        local1 = local1 + 0x1
        local2 = (local2 - 0xffffff80) & 0xffffffff


print(hex(local1))


Al restar **0xffffff80** a **ebp-0x8** de esto es x86 por lo que tenemos que truncar el resultado **0xffffffff

Obteniendo como resultado 

Flag = 0xf6



## Notas adicionales
## Referencias 
https://www.youtube.com/watch?v=R4r1cbBvPqk&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=54

https://dev.to/rooyca/picoctf-writeup-reverse-engineering-asm2-1659
