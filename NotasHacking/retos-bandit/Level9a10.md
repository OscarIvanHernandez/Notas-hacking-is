# Bandit level 9 → Level 10

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solucion
bandit9@bandit:~$ strings data.txt | grep ===
========== the*2i"4
========== password
Z)========== is
&========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$ exit

## Notas adicionales
Con strings obtenemos aquellos caracteres tipo string que pueden ser mostrados y junto a grep se filtran la lineas con los ===

## Referencias
https://www.educba.com/linux-string-command/#:~:text=String%20command%20in%20Linux%20will,be%20considered%20as%20one%20character.
