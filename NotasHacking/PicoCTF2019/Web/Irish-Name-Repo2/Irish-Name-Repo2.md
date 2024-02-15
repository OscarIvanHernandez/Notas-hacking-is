# Pico CTF2019 Web
## Objetivo
There is a website running at There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849
## Pistas
The password is being filtered.
## Solucion
1)
En la pagina login se usa la herramienta de inspeccion
2)
Ubicando la linea del html del debug se modifica el value de 0 a 1 y se lanza el login, habra que tener los campos con algun valor
3)
La inyeccion es detectada, aun proband la inyeccion en el username, se toma la sentencia SQL
4)
Se debe inyectar en el username admin' para ignorar el resto de la consulta
5)
Ahora al inyectar en el campo de username admin';
se lograr llegar al logged in!

picoCTF{m0R3_SQL_plz_fa983901}

## Notas Adicionales
Sí al inyectar admin'; en el username y en el password se mantiene el  "  ' or 1 == 1; " nos lanzara el SQLI detected
## Referencias
https://www.youtube.com/watch?v=1o53Bwty1E4&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=8