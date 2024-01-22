Możesz użyć polecenia `set_pixel` do sterowania poszczególnymi diodami LED w Sense HAT. Aby to zrobić, musisz podać poleceniu `set_pixel` zmienne `x` i `y`. Zmienna `x` wskazuje poziomą oś HAT i może mieć wartość pomiędzy `0` (po lewej) i `7` (po prawej). Zmienna `y` wskazuje pionową oś HAT i może mieć wartość pomiędzy `0` (po lewej) i `7` (na dole). Oznacza to, że współrzędne (`x, y`) = (`0, 0`) opisują lewą górną diodę LED, a (`x, y`) = (`7,7 `) opisują prawą dolną diodę LED.

![](images/coordinates.png)

Powyższa siatka odpowiada Raspberry Pi, gdy jest w ten sposób:

![](images/rpicoordinates.png)

Wypróbuj ten przykład ustawiania innego koloru w każdym rogu matrycy LED Sense HAT. Będziesz musiał użyć polecenia `set_pixel` w kodzie kilkukrotnie, w następujący sposób:

```python
from sense_hat import SenseHat

sense = SenseHat() # to polecenie czyści wszystkie piksele pozostawione na Sense HAT. Nie zawsze będziesz potrzebować tego kroku i możesz wybrać kiedy go dodać.

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Przetestuj ustawianie koloru różnych pikseli za pomocą emulatora Sense HAT: <iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
