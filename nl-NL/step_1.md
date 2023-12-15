Je kunt de opdracht `set_pixel` gebruiken om afzonderlijke LED's op de Sense HAT te bedienen. Om dit te doen, stel je de variabelen `x` en `y` in die de opdracht `set_pixel` gebruikt. `x` geeft de horizontale as van de HAT aan en kan een waarde hebben tussen `0` (links) en `7` (rechts). `y` geeft de verticale as van de HAT aan en kan een waarde hebben tussen `0` (bovenaan) en `7` (onderaan). Daarom adresseren de `x, y` coördinaten `0, 0` de LED linksboven en de `x, y` coördinaten `7, 7` de LED rechtsonder.

![](images/coordinates.png)

Het bovenstaande raster komt overeen met de Raspberry Pi wanneer het zo ligt:

![](images/rpicoordinates.png)

Probeer dit voorbeeld eens om een andere kleur in elke hoek van de LED-matrix van de Sense HAT in te stellen. Je moet het commando `set_pixel` meerdere keren in je code gebruiken, zoals hier:

```python
from sense_hat import SenseHat

sense = SenseHat () # Dit wist alle pixels die nog op de Sense HAT zijn achtergebleven. Je hebt deze stap mogelijk niet nodig en wilt mogelijk kiezen wanneer je deze wilt toevoegen.

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Test het instellen van de kleur van verschillende pixels met behulp van de Sense HAT-emulator: <iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
