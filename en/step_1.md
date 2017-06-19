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
