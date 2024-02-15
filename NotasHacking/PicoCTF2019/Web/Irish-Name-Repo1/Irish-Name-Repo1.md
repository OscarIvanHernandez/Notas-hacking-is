# Pico CTF2019 Web
## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!
## Pistas
Try to think about how the website verifies your login.
## Solucion
1)
En la pagina login se usa la herramienta de inspeccion
2)
Ubicando la linea del html del debug se modifica el value de 0 a 1 y se lanza el login, habra que tener los campos con algun valor
3)
Dando uso de la sentencia que aparece, se prepara una inyeccion de SQL 
4)
Se aplica la inyeccion SQL en el campo de password para el usuario admin en este caso
5)
picoCTF{s0m3_SQL_c218b685}
## Notas Adicionales
## Referencias
https://www.youtube.com/watch?v=0EDbUSDqrng&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=7
