# PicoCTF2022 Crypto
## Objetivo
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://artifacts.picoctf.net/c/534/leak.tar). The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.
## Pistas
Maybe other passwords will have hints about the leak?
## Solucion
1)
Se abren los archivos .txt almacenados en la carpeta leak/
y usando pluma, se usa la herramienta de buscar en el usernames.txt
para buscar el nombre cultiris
	captura

2)
Se busca en el passwords.txt el mismo numero de linea donde se ecnontraba el nombre cultris
	captura2

3)
El formato de la contaseña pareciera estar cifardo en ROT13
se usa ciberchef para desencriptar 
	captura3

picoCTF{C7r1F_54V35_71M3}

## Notas adicionales
## Referencias 

https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=Y3ZwYlBHU3tQN2UxU181NEkzNV83MVozfQ
