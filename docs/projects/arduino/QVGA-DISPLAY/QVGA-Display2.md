**Original document found at:**
===============================

https://playground2014.wordpress.com/arduino/qvga-display-2-2-tft-spi-240x320/

**QVGA DISPLAY 2.2 TFT SPI 240×320**
====================================

**Update 23.05.2016 – Using the SD card modul**
-----------------------------------------------

In the first tutorial (see below), I described the display. Please, read
this tutorial first, so you understand this part better.

This display has backside a SD card slot. Normally, this modul is not
connected. To use it, you must solder 4 pins.

**And now, be carefull! This pins works with 3.3V too! If you connect
this to 5V (arduino pins directly) you destroy your SD card!**

You must use the level converter!

We can connect multiple devices at the same time to the SPI interface.
So, we connect the display and the SD card modul to this interface. Be
sure, you connect the SD modul ports with the low level side!

![20160523\_191632](.//media/image4.jpg){width="5.5in"
height="3.111111111111111in"}

![qvga\_tft\_display1](.//media/image3.png){width="5.5in"
height="3.111111111111111in"}

And now, let us use the SD card module.

In the first tutorial, you used already two ADAFRUIT libraries. Now, we
need a third library, named “SD.h”.

You will find two great examples in your arduino IDE – “graphicstest”
and “spitfbitmap”. Both runs without changes!

Try it! The necessary bitmap for the second sketch is in the example
folder. Look there and copy it to your SD card (directly into the root
directory).

/\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\
This is an example sketch for the Adafruit 2.2" SPI display.\
This library works with the Adafruit 2.2" TFT Breakout w/SD card\
----&gt; http://www.adafruit.com/products/1480\
\
Check out the links above for our tutorials and wiring diagrams\
These displays use SPI to communicate, 4 or 5 pins are required to\
interface (RST is optional)\
Adafruit invests time and resources providing this open source code,\
please support Adafruit and open-source hardware by purchasing\
products from Adafruit!\
\
Written by Limor Fried/Ladyada for Adafruit Industries.\
MIT license, all text above must be included in any redistribution\
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*/\
\
\#include &lt;Adafruit\_GFX.h&gt; // Core graphics library\
\#include "Adafruit\_ILI9340.h" // Hardware-specific library\
\#include &lt;SPI.h&gt;\
\#include &lt;SD.h&gt;\
\
// TFT display and SD card will share the hardware SPI interface.\
// Hardware SPI pins are specific to the Arduino board type and\
// cannot be remapped to alternate pins. For Arduino Uno,\
// Duemilanove, etc., pin 11 = MOSI, pin 12 = MISO, pin 13 = SCK.\
\#define TFT\_RST 8\
\#define TFT\_DC 9\
\#define TFT\_CS 10\
\#define SD\_CS 4\
\
Adafruit\_ILI9340 tft = Adafruit\_ILI9340(TFT\_CS, TFT\_DC, TFT\_RST);\
\
...

**QVGA Display 2.2 TFT SPI 240×320**
------------------------------------

In this tutorial I show you, how you can use the TFT SPI display.

First, what is SPI?

SPI is the abbreviation for “Serial Peripheral Interface”. For this type
of communication, we need the following data ports:

MISO = Master In, Slave Out

MOSI = Master Out, Slave In

SCK = Serial Clock

SS = Slave Select

Our Arduino has already this port definition:

Port 11 = MOSI

Port 12 = MISO

Port 13 = SCK

Port 10 = SS

This is the set to communicate via SPI.

We need two additional ports for our display:

Port 9 = Data / Command selection

Port 8 = Reset (Low Level active)

So far, so good, but there is one problem:

The TFT display works with 3.3 V. Ok, this no problem, our arduino has
this voltage. **But we need 3.3V at the data ports too!** And here works
the arduino with 5V.

With 5V on ports 10, 11, 12 and 13 the display will be dark, no chance!

We solve the problem with a level converter. There are a lot of IC,
example the CD4050. I use in this tutorial two breakout boards from
sparkfun.

**Annotations:**

The LED pin is connected with 3.3V, Vcc too.

**Some Details:**

![2014-08-03 11.43.21](.//media/image2.jpg){width="4.166666666666667in"
height="2.3472222222222223in"}
![level\_converter](.//media/image6.jpg){width="2.8055555555555554in"
height="2.361111111111111in"}
![TFT\_SPI](.//media/image1.jpg){width="4.166666666666667in"
height="2.3472222222222223in"}
![QVGA\_TFT\_Display](.//media/image5.png){width="4.166666666666667in"
height="2.3472222222222223in"}

**The code:**

/\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\
This is an example sketch for the Adafruit 2.2" SPI display.\
This library works with the Adafruit 2.2" TFT Breakout w/SD card\
----&gt; http://www.adafruit.com/products/1480\
\
Check out the links above for our tutorials and wiring diagrams\
These displays use SPI to communicate, 4 or 5 pins are required to\
interface (RST is optional)\
Adafruit invests time and resources providing this open source code,\
please support Adafruit and open-source hardware by purchasing\
products from Adafruit!\
\
Written by Limor Fried/Ladyada for Adafruit Industries.\
MIT license, all text above must be included in any redistribution\
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*/\
\
\#include "SPI.h"\
\#include "Adafruit\_GFX.h"\
\#include "Adafruit\_ILI9340.h"\
\
\#if defined(\_\_SAM3X8E\_\_)\
\#undef \_\_FlashStringHelper::F(string\_literal)\
\#define F(string\_literal) string\_literal\
\#endif\
\
// These are the pins used for the UNO\
// for Due/Mega/Leonardo use the hardware SPI pins (which are
different)\
\#define \_sclk 13\
\#define \_miso 12\
\#define \_mosi 11\
\#define \_cs 10\
\#define \_dc 9\
\#define \_rst 8\
\
Adafruit\_ILI9340 tft = Adafruit\_ILI9340(\_cs, \_dc, \_rst);\
\
void setup() {\
tft.begin();\
\
tft.setRotation(1);\
testText();\
}\
\
void loop(void) {\
\
}\
\
\
unsigned long testText() {\
tft.fillScreen(ILI9340\_BLACK);\
tft.setCursor(20, 20);\
tft.setTextColor(ILI9340\_RED); tft.setTextSize(4);\
tft.println("Thank you!");\
tft.setCursor(20, 70);\
tft.setTextColor(ILI9340\_YELLOW); tft.setTextSize(2);\
tft.print("Adafruit tft.setTextColor(ILI9340\_WHITE);\
tft.print(" & ");\
tft.setTextColor(ILI9340\_GREEN);\
tft.println("Sparkfun");\
tft.setTextColor(ILI9340\_WHITE);\
tft.setTextSize(2);\
tft.println();\
tft.println("It's crazy! The display ");\
tft.println("works! ");\
tft.println();\
tft.print("Thank");\
tft.setTextColor(ILI9340\_YELLOW);\
tft.println("Adafruit");\
tft.setTextColor(ILI9340\_WHITE);\
tft.println("for the perfect libraries");\
tft.print("& thank you ");\
tft.setTextColor(ILI9340\_GREEN);\
tft.print("Sparkfun tft.setTextColor(ILI9340\_WHITE);\
tft.println("for");\
tft.println("the really simple to use");\
tft.println("Level Converter! ");\
}
