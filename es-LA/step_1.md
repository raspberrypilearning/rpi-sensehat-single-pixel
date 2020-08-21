Puedes usar el comando `set_pixel` para controlar cada LED en Sense HAT. Para hacer esto, puedes configurar las variables `x` e `y` con el comando `set_pixel`. `x` indica el eje horizontal del HAT, y puede tomar valores entre `0` (a la izquierda) y `7` (a la derecha). `y` indica el eje vertical del HAT, y puede tomar valores entre `0` (superior) y `7` (inferior). Therefore, the `x, y` coordinates `0, 0` address the top left-hand LED, and the `x, y` coordinates `7, 7` address the bottom right-hand LED.

![](images/coordinates.png)

The grid above corresponds with the Raspberry Pi when it is this way around:

![](images/rpicoordinates.png)

Let try out this example for setting a different colour in each corner of the Sense HAT's LED matrix. You will need to use the `set_pixel` command multiple times in your code, like this:

```python
from sense_hat import SenseHat

sense = SenseHat() # This clears any pixels left on the Sense HAT. You may not need this step and may want to choose when to add it in.

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Test setting the colour of different pixels using the Sense HAT Emulator: <iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen mark="crwd-mark"></iframe>
