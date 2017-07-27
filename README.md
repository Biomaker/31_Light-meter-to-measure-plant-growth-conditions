Here are some loose guidlines meant to give you an idea of what information we expect to find in each repository. Feel free to present your documentation in the most accessible/suitable order and style but you **must** include project data relating to the headings below, if relevant to your project. Also, include your final proposal in the top directory.

[**A very good example**](https://github.com/Biological-Microsystems-Laboratory/micropipette)

Consider using [GitHub for desktop](https://desktop.github.com/), the user interface and experience is so much better than the web version of Github, in my opinion.

Lastly, follow [these](https://pages.github.com/) instructions if you want to style your github repository into a webpage like [so](https://biomakers.github.io/Example-repo/).

## Synopsis

A summary of your project. This is the 150 word description from your proposal. Include your project banner and photos of team members.

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

## Installation, Maintenance and Testing Guide

Provide instructions on usage, describe a test scheme and show how to run the tests with code and hardware configuration examples with some representative results.

## License

A short snippet describing the license (MIT, Apache, etc.) you have chosen to use
