# P1-Vacuum_cleaner

04/10/25

David Pons Canet

## Objetivo

Desarollar un algoritmo que consiga que la aspiradora cubra el maximo espacio posible de una habitación.

Tenemos un bumper y un LIDAR de 180º.

## Resumen

Mi algoritmo se basa en, primero acercarse a una pared, para despues seguirla 'x' tiempo, y despues hacer un barrido con moviminentos aleatorios
durante 'y' timepo. Una vez acabado el barrido, se vuelve a buscar una pared y repite el proceso.

## Problemas y soluciones

Un o de los problemas que me he encontrado, ha sido alseguir la pared, en las esquinas exteriores, a veces se quedaba pillado entre girar derecha e izquierda, porque solo cogia una medida del laser de referencia y con eso daba algun problema, pero para solucionarlo he decidido hacer un promedio de las distancias de un rango del LIDAR, de la soguiente manera:

Otro de los problemas que me habian surgido, era que a veces, al pasar del barrido al seguir pared de nuevo, si el cambio era muy cerca de una pared, podia no detectarla bien o quedandose girando infinitamente porque detecta que no esta a la distancia que deberia.

Esto he podido solucionarlo metiendole un timer de RESET. Lo que hace es que si en 10 segundos de empezar a buscar la pared no la ha encontrado, vaya ligeramente para atras y despues vuelva a buscar la pared.

Ej: [Ver video de demostración](test/Screencast%20from%202025-10-04%2014-04-00.mp4)



Despues de muchas ejecuciones, tuve la idea de que si cada 'x' follow_wall le alargaba el tiempo de seguir la pared, podria audarme en algunos casos a alejarme mas de la zona donde estoy para poder llegar a una zona nueva y barrerla.

He podido observar que los armarios marrones no se detectan bien con el laser.distintas

## Tests

He incluido varias imagenes y un video de ejecuciones del algoritmo funcionado durante aproximadamamente 10 minutos.

Video ejecución: [Ver video de demostración](test/Screencast%20from%202025-10-04%2014-42-17.mp4)