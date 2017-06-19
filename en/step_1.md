The `x` and `y` variables can be used to control which individual LED the `set_pixel` command should change. **X** is horizontal and ranges from `0` on the *left* to `7` on the *right*. **Y** is vertical and ranges from `0` at the *top* to `7` on the *bottom*. Therefore, an `x, y` coordinate of `0, 0` is the *top left* and an `x, y` coordinate of `7, 7` is the *bottom right*.

![](images/coordinates.png)

You can get a different colour in each corner of the LED matrix. You will need to use the `set_pixel` command multiple times in your code like this:

```python
from sense_hat import SenseHat

sense = SenseHat()

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

<iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Drawing shapes and patterns on the LED matrix

You may be tempted to try and draw shapes or patterns using the `set_pixel` command over and over in your code. There is a `set_pixels` command though, and with it you can change all 64 LEDs using one line of code! For example, you could draw a Minecraft creeper face on the LED Matrix:

```python
from sense_hat import SenseHat

sense = SenseHat()

O = (0, 255, 0) # Green
X = (0, 0, 0) # Black

creeper_pixels = [
    O, O, O, O, O, O, O, O,
    O, O, O, O, O, O, O, O,
    O, X, X, O, O, X, X, O,
    O, X, X, O, O, X, X, O,
    O, O, O, X, X, O, O, O,
    O, O, X, X, X, X, O, O,
    O, O, X, X, X, X, O, O,
    O, O, X, O, O, X, O, O
]

sense.set_pixels(creeper_pixels)
```

<iframe src="https://trinket.io/embed/python/d6ccea808e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

You can even use more than two colours, like in this example of Steve from Minecraft:

```python
from sense_hat import SenseHat

sense = SenseHat()

B = (102, 51, 0)
b = (0, 0, 255)
S = (205,133,63)
W = (255, 255, 255)

steve_pixels = [
    B, B, B, B, B, B, B, B,
    B, B, B, B, B, B, B, B,
    B, S, S, S, S, S, S, B,
    S, S, S, S, S, S, S, S,
    S, W, b, S, S, b, W, S,
    S, S, S, B, B, S, S, S,
    S, S, B, S, S, B, S, S,
    S, S, B, B, B, B, S, S
]

sense.set_pixels(steve_pixels)
```
