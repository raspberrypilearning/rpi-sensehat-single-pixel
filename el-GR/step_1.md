Μπορείς να χρησιμοποιήσεις την εντολή `set_pixel` για τον έλεγχο μεμονωμένων LED στο Sense HAT. Για να το κάνεις αυτό, ορίζεις τις `x` και `y` μεταβλητές στη `set_pixel` εντολή. Το `x` αναφέρεται στον οριζόντιο άξονα του HAT και μπορεί να έχει τιμή μεταξύ `0` (στα αριστερά) και `7` (στα δεξιά). Το `y` αναφέρεται στον κατακόρυφο άξονα του HAT και μπορεί να έχει τιμή μεταξύ `0` (πάνω) και `7` (κάτω). Συνεπώς το σημείο `x, y` με συντεταγμένες `0, 0` αναφέρεται στο επάνω αριστερό LED και το `x, y` με συντεταγμένες `7, 7` αναφέρεται στο κάτω δεξιά LED.

![](images/coordinates.png)

Το παραπάνω πλέγμα αντιστοιχεί στο Raspberry Pi όταν συμβαίνει αυτό:

![](images/rpicoordinates.png)

Δοκίμασε το παρακάτω παράδειγμα για να ορίσεις ένα διαφορετικό χρώμα σε κάθε γωνία του πίνακα LED του Sense HAT. Θα πρέπει να χρησιμοποιήσεις την `set_pixel` εντολή πολλές φορές στον κώδικά σου, όπως παρακάτω:

```python
from sense_hat import SenseHat

sense = SenseHat () # Αδειάζει την οθόνη από τυχόν εικονοστοιχεία που απέμειναν στο Sense HAT. Ίσως δεν χρειάζεσαι αυτό το βήμα και μπορεί να θέλεις να επιλέξεις το πότε και που θα το προσθέσεις.

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Δοκίμασε να ρυθμίσεις το χρώμα σε διαφορετικά pixel χρησιμοποιώντας το Sense HAT Emulator: 
<iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen mark="crwd-mark"></iframe>
