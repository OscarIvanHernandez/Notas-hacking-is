# Pico CTF20219 Web
## Objetivo

## Pistas
## Solucion

1)
Desde el inspector en el apartado de red, entramos a una peticion GET, como en la captura_1

2)
Se modifica en la peticion el User-Agent como picobrowser y se reenvia

3)
Se abre la respuesta de la nueva peticion, en donde se encuentra la bandera

picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}

## Notas adicionales
Aprovechando del archivo robots.txt, se encuentra la ruta en donde esta escondida la bandera
## Referencias