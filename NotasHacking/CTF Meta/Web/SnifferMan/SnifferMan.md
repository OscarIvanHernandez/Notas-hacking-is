# CTF META
## Objetivo
My organization has learned about cybersecurity the hard way in recent years.

<�div class="row challenge-files text-center pb-3"> <�div class="col-md-4 col-sm-4 col-xs-12 file-button-wrapper d-block"> <�a class="btn btn-info btn-file mb-1 d-inline-block px-2 w-100 text-truncate" href="https://ctfd2022.anuies.mx/files/0f9d7f7e61dc57903dba36eef843b39b/challenge.pcapng?token=eyJ1c2VyX2lkIjoxODgzLCJ0ZWFtX2lkIjo1MDYsImZpbGVfaWQiOjI0fQ.Y1A2bQ.YUQ1eukZ9c1AB9p2dTi3gq-CEqM"> <�i class="fas fa-download"><�/i> <�small> challenge.pcapng <�/small> <�/a> <�/div> <�/div>

## Pistas

## Solucion

1)
En whireshark se sigue el flujo de datos TCP
	captura1

2)
Se recorren los paquetes, y se llega hasta el paquete 8 en donde se aprecia una forma de bandera pero codificada
	captura2

3)
Usando CyberChef se decodifica en ROT13 de cifrado 8
	captura3
	
flagMX{M2n_9n_Th1_M9ddl1_2tt2ck}

4)
Siguiendo la logica del mensaje se corrije para darle sentido

flagMX{M4n_1n_Th3_M1ddl3_4tt4ck}
## Notas adicionales
## Referencias