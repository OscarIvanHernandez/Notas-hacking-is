# PicoCTF2019 Forensic
## Objetivo
This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.
## Pistas
What is a hex editor?
## Solucion
┌─[oscar@oscar-parrot]─[~/forensic_2019]
└──╼ $mkdir GloryOfTheGarden
┌─[oscar@oscar-parrot]─[~/forensic_2019]
└──╼ $cd GloryOfTheGarden/
┌─[oscar@oscar-parrot]─[~/forensic_2019/GloryOfTheGarden]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg 

...

┌─[✗]─[oscar@oscar-parrot]─[~/forensic_2019/GloryOfTheGarden]
└──╼ $xxd garden.jpg

...

	00230540: eeef 53ae 8620 31b8 751f 9514 f7fb cff5  ..S.. 1.u.......
	00230550: a2bb bdac 9687 98e4 d3b2 e87f ffd9 4865  ..............He
	00230560: 7265 2069 7320 6120 666c 6167 2022 7069  re is a flag "pi
	00230570: 636f 4354 467b 6d6f 7265 5f74 6861 6e5f  coCTF{more_than_
	00230580: 6d33 3374 735f 7468 655f 3379 3333 6464  m33ts_the_3y33dd
	00230590: 3265 4546 357d 220a                      2eEF5}".
┌─[oscar@oscar-parrot]─[~/forensic_2019/GloryOfTheGarden]
└──╼ $

	picoCTF{more_than_m33ts_the_3y33dd2eEF5}

	Si hacemos uso de un editor hex, podremos realizar una busqueda dentro, oh bien mostrar todo el contenido, donde se puede observar la bandera a un lado derecho 

## Notas adicionales

## Referencias
