Sense HATの個々のLEDを制御するには、`set_pixel`コマンドを使用します。 これを行うために、`set_pixel`コマンドが必要とする変数`x`および`y`を設定します。 `x`はHATの水平方向の位置を示し、`0`(左側)と`7`(右側)の間の値をとることができます。 `y`はHATの垂直方向の位置を示し、`0`(上側)と`7`(下側)の間の値をとることができます。 したがって、` x, y `座標` 0, 0 `は左上のLEDを、` x, y `座標` 7, 7 `は右下のLEDを指し示します。

![](images/coordinates.png)

上のグリッドは、Raspberry Piがこのような向きになっているときのものです。

![](images/rpicoordinates.png)

Sense HATのLEDマトリックスのそれぞれの角に別々の色を設定する例を試してみましょう。 次のようにコード内で`set_pixel`コマンドを複数回使用する必要があります。

```python
from sense_hat import SenseHat

sense = SenseHat() # Sense HATに残っているピクセルをクリアします。 この手順は必要なく、いつ追加するかを選択することもできます。

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Sense HATエミュレータを使用して、さまざまなピクセルの色の設定をテストします。 <iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen mark="crwd-mark"></iframe>
