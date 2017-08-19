
## Synopsis


<img src="images/banner2.jpg" alt="image"/>

<img src="images/Jennifer-Deegan.jpg" alt="image"/>
<img src="images/Tim Deegan.jpg" alt="image"/>

<p>

This project is an investigation into the effect of light intensity on the health of plants and people, or more specifically, gardens and gardeners. 

I have spent my life moving back and forth between the north of the UK and the south, and even as far as France, and I have always been puzzled about the incredible effect that geographical location has on plant growth in my gardens, and on the physical health of my friends. 

As a child, I moved from Glasgow to Paris and back before the age of 9 and was acutely aware of the changes that I saw my own physiology and on the plant life around me. This same observation held every time I visited Scotland as an adult, through verious seasons and changes of weather, and then reversed as I returned to work in the south. In recent years, as my community and I have matured, I have become aware that certain more serious health problems are more common in the north, and that these are almost certainly brought on partly by lack of sun exposure. At the same time, I have now become a garden owner myself. I now struggle daily with very different gardening challenges in the south, from those of my garden-owning friends in the north. 

Throughout this process, I have noticed that gardeners and dog walkers seem disproportionately insulated from the health problems associated with northern living. This is presumably because their hobbies force them outside every day, regardless of the weather. 

I know that the difference in human health and plant life, between north and south, is almost certainly to do with light levels. However, I am constantly frustrated by my own inability to accurately measure light intensity with my own eyes. I feel that if I could properly judge how much sunlight I have had in each day, I could make sure to get enough, and teach others to do the same. I would then also be far better able to judge which spots would give a good home to which plant species in my garden. However, this is not an easy call to make. 

The difficulty in judging light intensity is caused by the accommodation of the pupil of the eye. The pupils adjust naturally to light intensity. Therefore in any given situation, there seems to be just enough light. The very adaptability of the human being to living in any light intensity, makes it just a little harder for us to live really well, in any light intensity.

My hope in this project is to build a light meter that will enable me to accurately measure how much light there is in my environment in a range of different situations and at different times of day and year. My hope is that this will better enable me to manage my own physiology and also my own garden, with much less guesswork. I am living in Cambridge, but I am helped in the project by my life-long friend Catriona Ferris, who lives in the west of Scotland. She is going to take matching readings to investigate the light intensity in her own environment. Catriona and I are both keen gardeners and we have already investigated and compared most of the other growing conditions in our very different gardens, discussing every detail over facebook. This year we will investigate light conditions, to try to find insight into how light intensity affects not just our plants, but also our own lives and those of our communities.

The design that I have chosen for the light-meter is built from an Arduino and associated parts. My hope is that if we find really interesting results, then this could be turned into a population-level educational tool.  It could perhaps be distributed via a magazine like Gardeners' World Magazine or via a tv program like Springwatch, underpinning a national study of light levels in lives and gardens. That way the keen maker-teenagers of the country could build these machines and educate everybody else around them about the nature of light, and its effect on their gardens and health. 


## Software

<p>
#include <Wire.h><br>
#include <BH1750.h><br>
#include "rgb_lcd.h"<br>
  </p><p>
rgb_lcd lcd;<br>
const int colorR = 0;<br>
const int colorG = 0;<br>
const int colorB = 0;<br>
</p><p>
BH1750 lightMeter;<br>
</p><p>
void setup() {<br>
  Serial.begin(9600);<br>
  lightMeter.begin();<br>
  Serial.println("Running...");<br>
  // set up the LCD's number of columns and rows:<br>
  lcd.begin(16, 2);<br>
  lcd.setRGB(colorR, colorG, colorB);<br>
  // Print a message to the LCD.<br>
  lcd.print("Light intensity");<br>
}<br>
  </p><p>
void loop() {<br>
  uint16_t lux = lightMeter.readLightLevel();<br>
  Serial.print("Light: ");<br>
  Serial.print(lux);<br>
  Serial.println(" lx");<br>
</p><p>
  // Clear the bottom line of the LCD<br>
  lcd.setCursor(0,1);<br>
  lcd.print("          ");<br>
</p><p>
  // For LCD: set the cursor to column 0, line 1<br>
  // (note: line 1 is the second row, since counting begins with 0):<br>
  lcd.setCursor(0, 1);<br>
  // print the number of seconds since reset:<br>
  lcd.print(lux);<br>
  delay(1000);<br>
}<br>
</p>
  
## Hardware

Explain how the hardware components (if any) of your project function as concisely as possible, including a short description of fabrication and assembly. Component suppliers and part numbers should be provided separately in a bill of materials, in a 'Hardware Folder'.</p><p>

Notes on hardware to be moved to the Hardware folder:
</p><p>
- <a href="https://www.amazon.co.uk/d/Electronics-Photo/40pcs-Dupont-Male-Female-20cm-Jumper-Connectors/B013EW65H2/ref=sr_1_1?ie=UTF8&qid=1501469205&sr=8-1&keywords=male+to+female+jumper+leads"> 5 jumper leads, male to female</a> - £1.99+P&P<br>
- <a href="https://makersify.com/products/dfrobot-light-sensor-bh1750">one light sensor BH1750</a> - £14+P&P<br>
- <a href="https://www.amazon.co.uk/Arduino-A000066-UNO/dp/B008GRTSV6/ref=sr_1_4?s=computers&ie=UTF8&qid=1501468175&sr=1-4&keywords=arduino+uno">One arduino Uno</a> - £17.30+P&P<br>
- <a href="https://www.seeedstudio.com/Grove-LCD-RGB-Backlight-p-1643.html">One Grove-LCD RGB Backlight v4.0</a> - £10.61+P&P<br>
- <a href="http://www.robotshop.com/uk/adafruit-battery-holder-barrel-jack.html?gclid=Cj0KCQjwlMXMBRC1ARIsAKKGuwgjdagw_J_4zrTdrNKmqMNNupCF1OF1kEguYkfuQn4ah6_1nsIECt8aApqwEALw_wcB">Battery holder + wire to power the Arduino.</a> AA batteries ideal as rechargables are easy to obtain. 6 x AA batteries are needed to give 9V. Four AAs is not enough to power the screen - £4.66+P&P<br>
</p><p>
  
The light sensor measures from 0 to 100,000 lux, which is a very good range for measuring from the darkest room in a house to the brightest day outside.   

</p><p>
Here are some initial images of the hardware. These will be replaced with better ones once the images are ready.
</p><p>
<img src="images/IMG_6600.JPG" alt="image"/>
<img src="images/IMG_6601.JPG" alt="image"/>
<img src="images/IMG_6588.JPG" alt="image"/>
<img src="images/IMG_6597.JPG" alt="image"/>
<img src="images/IMG_6598.JPG" alt="image"/>
<img src="images/IMG_6599.JPG" alt="image"/>


## Installation, Maintenance and Testing Guide

Using the machine is very easy. Just plug it all togehter. Plug into the computer with the Arduino's usb cable. Run the arduino software and past the code above into the code window. Then press the button (top left) to upload the code to the Arduino. Then unplud from the computer and plug in the battery and walk outside. The machine should automatically start displaying the light intensity on the lcd screen. The table below gives some example readings. 


## Some light meter readings

### Maps of test areas

<img src="images/cambridge.jpg" alt="image"/>

### August

14th August, 3.20pm 21 degrees C, in my own garden;

| location | light intensity in lux  |
| --------- | ------------------------ |
| dining room, 2m from french windows that face east, doors open      |    360 |
| same location but with me between the sensor and door, casting shade, doors open   |       79 |
| almost same location but now sitting 1m from open door     |    3000 |
| sitting on the step of the french windows, sensor facing up    |     8000 |
| same location, sensor facing down       |  2000 |
| out in the garden, sensor facing up, 70% thin cloud     |    20000 |
| same, but with a piece of paper held 15cm above to shade sensor  |     9300 |
| under the pear tree     |    5000 |
| in greenhouse    | 7200 |
| under a pumpkin leaf 2m from greenhouse  |   2000 |
| next to the pumpkin leaf    |      11600 |

14th August, 22.30, In dining room, with curtains shut.

| location | light intensity in lux  |
| --------- | ------------------------ |
| Sitting at computer. Brightness measured at my eyes, pointing to computer. Brightness turned up  | 35 |
| As above, but brightness turned down | 29 |

15th August, 18.55

| location | light intensity in lux  |
| --------- | ------------------------ |
| In garden, blue sky but in shade of the house  | 1900 |
| Sitting at the computer | 178 |


16th August, 16.27

| location | light intensity in lux  |
| --------- | ------------------------ |
| Direct sunlight, blue sky  | 54500 |




## License

i have no idea what to do with this bit. 
