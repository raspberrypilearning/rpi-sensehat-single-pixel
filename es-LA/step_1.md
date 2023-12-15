Puedes usar el comando `set_pixel` para controlar cada LED en Sense HAT. Para hacer esto, puedes configurar las variables `x` e `y` con el comando `set_pixel`. `x` indica el eje horizontal del HAT, y puede tomar valores entre `0` (a la izquierda) y `7` (a la derecha). `y` indica el eje vertical del HAT, y puede tomar valores entre `0` (superior) y `7` (inferior). Por lo tanto, las coordenadas `x,y` (`0,0`) se refieren a la parte alta a la izquierda del LED, las coordenadas `x,y` (`7,7`) se refieren a la parte baja a la derecha del LED.

![](images/coordinates.png)

La cuadrícula de arriba corresponde con el Raspberry Pi cuando se ve de esta manera:

![](images/rpicoordinates.png)

Prueba este ejemplo para configurar un color diferente en cada esquina de la matriz LED de Sense HAT. Necesitarás usar el comando `set_pixel` varias veces en tu código, como este:

```python
desde sense_hat importa SenseHat

sense = SenseHat() # Esto borra cualquier pixel dejado en el SenseHAT. Puede que no necesites este paso y que quieras elegir cuándo añadirlo.

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Prueba elegir el color de los distintos pixeles al usar el emulador de SenseHAT: <iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
