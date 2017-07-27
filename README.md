
## Synopsis


<img src="images/banner2.jpg" alt="image"/>

<img src="images/Jennifer-Deegan.jpg" alt="image"/>
<img src="images/Tim Deegan.jpg" alt="image"/>


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

Explain how the hardware components (if any) of your project function as concisely as possible, including a short description of fabrication and assembly. Component suppliers and part numbers should be provided separately in a bill of materials, in a 'Hardware Folder'.

Here are some initial images of the hardware. These will be replaced with better ones once the images are ready.

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
