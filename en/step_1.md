You can use the `set_pixel` command to control individual LEDs on the Sense HAT. To do this, you set the `x` and `y` variables the `set_pixel` command takes. `x` indicates the HAT's horizontal axis, and can have a value between `0` (on the left) and `7` (on the right). `y` indicates the HAT's vertical axis, and can have a value between `0` (at the ltop) and `7` (at the bottom). Therefore, the `x, y` coordinates `0, 0` address the top left-hand LED, and the `x, y` coordinates `7, 7` address the bottom right-hand LED.

![](images/coordinates.png)

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

Test setting the colour of different pixels using the Sense HAT Emulator:

<iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
