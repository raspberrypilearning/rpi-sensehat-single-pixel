Sense HAT의 각각의 LED를 제어하기 위해 `set_pixel` 명령어를 사용할 수 있습니다. 이렇게 하려면 `set_pixel` 명령어에 사용되는 `x`와 `y`변수를 설정하세요. `x`는 HAT의 가로 축을 나타내며, 좌측 `0` 과 우측 `7` 사이의 값을 가질 수 있습니다. `y`는 HAT의 세로 축을 나타내며, 위쪽 `0` 과 아래쪽 `7` 사이의 값을 가질 수 있습니다. 따라서 `x, y` 좌표 `0, 0` 은 왼쪽 상단 LED를 가리키며, `x, y` 좌표 `7, 7` 은 우측 상단 LED를 가리킵니다.

![](images/coordinates.png)

위의 격자는 Raspberry Pi에서 다음과 같은 경우에 해당합니다.

![](images/rpicoordinates.png)

Sense HAT의 LED 매트릭스의 각 모서리에서 다른 색상을 설정하기 위해 이 예를 사용해 보십시오. 코드에서 다음과 같이 `set_pixel` 명령을 여러 번 사용해야 할 것입니다.

```python
from sense_hat import SenseHat

sense = SenseHat() #Sense HAT에 남아 있는 모든 픽셀이 지워집니다. 이 단계가 필요하지 않을 수 있으며 언제 추가할 지 선택할 수 있습니다.

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Sense HAT 에뮬레이터를 사용하여 다양한 픽셀의 색상을 테스트해보세요. <iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
