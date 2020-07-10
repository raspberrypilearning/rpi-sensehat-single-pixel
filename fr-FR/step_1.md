Tu peux utiliser la commande `set_pixel` pour contrôler les LEDs individuelles sur le Sense HAT. Pour faire cela, tu définis les variables `x` et `y` que prend la commande `set_pixel`. `x` indique l'axe horizontal du HAT, et peut avoir une valeur entre `0` (à gauche) et `7` (à droite). `y` indique l'axe vertical du HAT, et peut avoir une valeur entre `0` (en haut) et `7` (en bas). Par conséquent, les coordonnées `x, y`  `0, 0` adressent la LED en haut à gauche, et les coordonnées `x, y` `7, 7` adressent la LED en bas à droite.

![](images/coordinates.png)

La grille ci-dessus correspond au Raspberry Pi quand c'est de cette façon :

![](images/rpicoordinates.png)

Essaie cet exemple pour définir une couleur différente dans chaque coin de la matrice LED de Sense HAT. Tu devras utiliser la commande `set_pixel` plusieurs fois dans ton code, comme ceci :

```python
from sense_hat import SenseHat

sense = SenseHat() # Cela efface tous les pixels restants sur le Sense HAT. Tu n'as peut-être pas besoin de cette étape et tu peux choisir quand l'ajouter.

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Teste la définition de la couleur des différents pixels en utilisant l'émulateur Sense HAT : 
<iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen mark="crwd-mark"></iframe>
