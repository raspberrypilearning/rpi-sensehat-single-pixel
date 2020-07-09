आप `set_pixel` कमांड का उपयोग कर सकते हैं Sense HAT पर व्यक्तिगत LED को नियंत्रित करने के लिए। ऐसा करने के लिए, आप `x` और `y` वेरियबल सेट करें जिससे `set_pixel` आज्ञा लेता है। `x` HAT की क्षैतिज अक्ष को संकेत करता है, और उसका मान`0` (बाईं तरफ) और `7` (दायीं तरफ) के बीच हो सकता है। `y` HAT की लंबरूप अक्ष को संकेत करता है, और उसका मान`0` (शीर्ष पर) और `7` (तल पर) के बीच हो सकता है। इसलिए, `x, y` समन्वय `0, 0` संबोधित करता है ऊपरी बाएं हाथ का LED, और `x, y` समन्वय `7, 7` नीचे दाएं हाथ के LED को संबोधित करता है।

![](images/coordinates.png)

ऊपरी ग्रिड Raspberry Pi के साथ मेल खाता है जब यह इस तरह से होता है:

![](images/rpicoordinates.png)

Sense HAT के LED मैट्रिक्स के प्रत्येक कोने में एक अलग रंग सेट करने के लिए इस उदाहरण को आज़माएं। आपको `set_pixel` कमांड का अपने कोड में कई बार उपयोग करना होगा, इस तरह से:

```python
from sense_hat import SenseHat

sense = SenseHat() #इससे Sense HAT पर छोड़ा गया कोई भी पिक्सेल (pixel) साफ़ हो जाता है। आपको इस चरण की आवश्यकता नहीं हो सकती है और इसे कब जोड़ना है, यह आप चुन सकते हैं।

sense.clear()
sense.set_pixel(0, 0, 255, 0, 0)
sense.set_pixel(0, 7, 0, 255, 0)
sense.set_pixel(7, 0, 0, 0, 255)
sense.set_pixel(7, 7, 255, 0, 255)
```

Sense Hat एमुलेटर का उपयोग करके विभिन्न पिक्सेल (pixel) के रंग को सेट करके देखें: <iframe src="https://trinket.io/embed/python/78c2595904" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen mark="crwd-mark"></iframe>
