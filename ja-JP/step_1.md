Sense HATの個々のLEDを制御するには、`set_pixel`コマンドを使用します。 これを行うために、`set_pixel`コマンドが必要とする変数`x`および`y`を設定します。 `x`はHATの水平方向の位置を示し、`0`(左側)と`7`(右側)の間の値をとることができます。 `y`はHATの垂直方向の位置を示し、`0`(上側)と`7`(下側)の間の値をとることができます。 したがって、` x, y `座標` 0, 0 `は左上のLEDを、` x, y `座標` 7, 7 `は右下のLEDを指し示します。

![](images/coordinates.png)

上のグリッドは、Raspberry Piがこのような向きになっているときのものです。

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
