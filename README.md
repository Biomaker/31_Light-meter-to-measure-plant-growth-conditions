
## Synopsis


<img src="images/banner2.jpg" alt="image"/>

<img src="images/Jennifer-Deegan.jpg" alt="image"/>
<img src="images/Tim Deegan.jpg" alt="image"/>

<p>
My aim in this project is to enable teenage (and other) gardeners to consider how the growing conditions in their gardens compare with those of the TV gardens shown in Gardeners' World and the Beechgrove Garden. Teenage gardens are a group that horticulturalists and the gardening media are particularly keen to engage at the moment, and I hope that this project will help with that. 
</p><p>
For young gardeners it can be frustrating to see perfect tv gardens and to be unclear about what the difference between those tv gardens and the home gardens actually are. In fact their are many differences, such as the fertiliser and water content of the soil, the temperature and length of growing season in different geographical areas, the depth of soil, and the domninance of certain pests, such as aphids, pigeons and even deer. 
</p><p>
However, one difference that is really hard to quantify is light intensity. This is particularly difficult to grasp as the human eye is especially good at compensating for differences in light intensity. This is done by dilating the pupil of the eye by exactly the correct amount to make the current brightness of light seem just right. 
</p><p>
The accommodation of the human eye means that we are often unaware that we may be in really very dim, or very bright light. It also makes it hard to spot that a house plant might be really struggling to capture adequate light, while another plant just outside an adjacent window may be struggling with excess light, causing breakdown of the photosystems in its leaves. 
</p><p>
The horticultural industry contributes to this lack of clarity by simply taking about "shade", "full sun", and "partial shade" without giving any more clarity about exactly what this means in any standard unit of light intensity. It generally talks about the number of hours of full sun received, but my intuition is that 6 hours of full sun would be a very different thing in Orkney, from 6 hours of full sun received in Kent, especially during the winter. 
</p><p>
The light meter construction shown here, attempts to address this problem somewhat by allowing people to consider their own gardening and light conditions. The light meter is made from standard, easily bought parts. I have chosen the parts because the are cheap and easy to put together, the light sensor detects the correct range of light intensity, and the code is very easy to use and debug. 
</p><p>
My hope is that this how-to could be published by a gardening magazine like Gardeners' World Magazine, and that it could encourage many young gardeners to build their own light meter and measure the light conditions that are underpinning or undermining their growing success.
</p><p>
I would love to see this project published as a citizen-science project in which people who do build the light meter could then report their gardening light conditions on a website and that the information could be collated and the reported back in a later issue. This would help people to test whether the brightest spot in a garden in one area of the country might have the same sort of light intensity as the shadiest spot in a garden in another part of the country. This kind of information would help people to choose appropriate plants for their gardens, and to modify the conditions of growth, if they need to. 
</p><p>
I anticipate that the understanding of light conditions that this article brings would also be very instructive for those who have health problems that are conspicuously better in summer and worse in winter. I hope that this new knowledge would help people to make more informed choices about how much time they spend in the garden to support their winter health, and at what period of the day they do their gardening, for the best effect. The light meter might, in effect, become a low cost bio-wearable device to help people gauge how much sunshine they have had on any given day in winter, enabling them to optimise their winter sun exposure. 
  </p><p>
I anticipate that before publishing the article it would be helpful to negotiate a good price for the complete kit that is needed and that an order form could be included with the article so that readers could order the necessary parts very easily. 
</p><p>
This project could perhaps be followed up by further adrunio-based projects to measure temperature and other factors in plant growth.
</p><p>
The kind of results that might be found are explained helpfully in this document: http://www.ccfg.org.uk/conferences/downloads/P_Burgess.pdf.
</p><p>



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
- <a href="https://www.amazon.co.uk/Conductor-Female-Jumper-Color-Ribbon/dp/B00ATMHU525"> jumper leads, male to female</a><br>
- <a href="https://www.dfrobot.com/">one light sensor BH1750</a><br>
- <a href="https://www.amazon.co.uk/Arduino-A000066-UNO/dp/B008GRTSV6/ref=sr_1_4?s=computers&ie=UTF8&qid=1501468175&sr=1-4&keywords=arduino+uno">One arduino Uno</a><br>
- <a href="https://www.seeedstudio.com/Grove-LCD-RGB-Backlight-p-1643.html>One Grove-LCD RGB Backlight v4.0</a><br>
- <a href="https://www.dfrobot.com/product-500.html">One battery + wire to power the Arduino.</a> AA batteries ideal as rechargables are easy to obtain.<br>

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

Provide instructions on usage, describe a test scheme and show how to run the tests with code and hardware configuration examples with some representative results.

## License

A short snippet describing the license (MIT, Apache, etc.) you have chosen to use
