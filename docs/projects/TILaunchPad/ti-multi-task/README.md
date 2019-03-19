
## Oct 6, 2016 TI LaunchPad MS432 Multi-Tasking Demo  

[Pictures and short video](https://goo.gl/photos/MWqLFTNm54uBTmXz8) (early stage) showing the Demo for Oct 6th 2016 using the MSP432 multi-tasking board  

Video was before adding the Nokia 5110 screen, temperature sensor, and last 2 LEDs.  

## Current version of demo.

7 Blinking LEDs at different rates  
1 LED (in two threads) blink Green then Blue - showing the timing doesn’t change  
6 LEDs Fading at different rates and times  
3 Ultra Sonic Ping Sensors  
Nokia 5110 SPI screen  
DHT11 Temperature sensor  
A counting thread  
And a serial print to console thread  

All the leds are in there own thread, I count a total of 22 threads, plus the main thread which I used to setup some of the variables, serial port, lcd screen, etc  

## Libraries need (Which were a little hard to find)
[Nokia 5110](http://forum.43oh.com/topic/1312-nokia-5110-display/) (for the Launchpad)  
[DHT11 library] (https://forum.43oh.com/topic/2873-energia-library-ladyadas-dht-library-ported/).  

I started a repository for demos and projects using the TI Launchpad boards.  
[GitHub](https://github.com/automation-technology-club/TILaunchPad-Projects)  

