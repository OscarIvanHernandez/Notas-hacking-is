# Pico CTF2019 Web
## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849
## Pistas
## Solucion
1)
En la pagina login se usa la herramienta de inspeccion
2)
Ubicando la linea del html del debug se modifica el value de 0 a 1 y se lanza el login, se agrega un passoword aleatorio
3)
Al ver el resultado en la sentencia SQL del password, nos podemos percatar que esta esta encriptada en rot13
4)
Se comprueba que la encriptacion sea rot13 con la ayuda de la herramienta cyberchef
5)
En el password se inyecta " ' or 1 == 1; " encriptado en rot13
' be 1 == 1;

## Notas Adicionales
## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=JyBiZSAxPT0xOw
https://www.youtube.com/watch?v=H29JbY_KEYU&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=9