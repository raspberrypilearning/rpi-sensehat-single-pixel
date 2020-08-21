Puedes usar el comando `set_pixel` para controlar LEDs de forma individual en el Sense HAT. Para hacer esto, configura las variables `x` e `y` que toma el comando `set_pixel`. ` x ` indica el eje horizontal del HAT y puede tener un valor entre ` 0 ` (a la izquierda) y ` 7 ` (a la derecha). ` y ` indica el eje vertical del HAT y puede tener un valor entre ` 0 ` (en la parte superior) y ` 7 ` (en la parte inferior). Por lo tanto, las coordenadas ` x, y ` igual a ` 0, 0 ` se corresponden al LED superior izquierdo y las coordenadas ` x, y ` igual a ` 7, 7 ` se corresponden al LED inferior derecho.

![](images/coordinates.png)

La cuadrícula de arriba se corresponde con la Raspberry Pi cuando esta colocada de esta forma:

![](images/rpicoordinates.png)

Prueba este ejemplo para ajustar un color diferente en cada esquina de la matriz de LEDs del Sense HAT. Necesitarás usar el comando `set_pixel` varias veces en tu código, así:

```python
from sense_hat import SenseHat

sense = SenseHat() # Esto borra los píxeles que queden en SenseHAT. Es posible que no necesites este paso y que desees elegir cuándo agregarlo.

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Prueba a configurar el color de diferentes píxeles con el Emulador de Sense HAT: <iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen mark="crwd-mark"></iframe>
