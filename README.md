Here are some loose guidlines meant to give you an idea of what information we expect to find in each repository. Feel free to present your documentation in the most accessible/suitable order and style but you **must** include project data relating to the headings below, if relevant to your project. Also, include your final proposal in the top directory.

[**A very good example**](https://github.com/Biological-Microsystems-Laboratory/micropipette)

Consider using [GitHub for desktop](https://desktop.github.com/), the user interface and experience is so much better than the web version of Github, in my opinion.

Lastly, follow [these](https://pages.github.com/) instructions if you want to style your github repository into a webpage like [so](https://biomakers.github.io/Example-repo/).

## Synopsis

A summary of your project. This is the 150 word description from your proposal. Include your project banner and photos of team members.

## Software


#include <Wire.h>
#include <BH1750.h>
#include "rgb_lcd.h"

rgb_lcd lcd;
const int colorR = 0;
const int colorG = 0;
const int colorB = 0;

BH1750 lightMeter;

void setup() {
  Serial.begin(9600);
  lightMeter.begin();
  Serial.println("Running...");
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  lcd.setRGB(colorR, colorG, colorB);
  // Print a message to the LCD.
  lcd.print("Light intensity");
}

void loop() {
  uint16_t lux = lightMeter.readLightLevel();
  Serial.print("Light: ");
  Serial.print(lux);
  Serial.println(" lx");

  // Clear the bottom line of the LCD
  lcd.setCursor(0,1);
  lcd.print("          ");

  // For LCD: set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.setCursor(0, 1);
  // print the number of seconds since reset:
  lcd.print(lux);
  delay(1000);
}

## Hardware

Explain how the hardware components (if any) of your project function as concisely as possible, including a short description of fabrication and assembly. Component suppliers and part numbers should be provided separately in a bill of materials, in a 'Hardware Folder'.

## Installation, Maintenance and Testing Guide

Provide instructions on usage, describe a test scheme and show how to run the tests with code and hardware configuration examples with some representative results.

## License

A short snippet describing the license (MIT, Apache, etc.) you have chosen to use
