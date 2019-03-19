# Another Wireless Demo

Various libraries are needed depending on what/which wireless technology you will be using.  

These all pretty much do the same thing, as the demo was to see how far each could transmit inside a building with walls, and metal sheveling.  

The LoRa demo is different in it transmits the temperature to a oled receiver.  
The reason was I already had that code written and working so it was easier to just reuse it.  

The other sketches, the transmitter have a button that is pushed, and the receiver will blink a LED.  

5 Different technologies are used:  
LoRa (915Mhz), ESP8266 Wifi MESH (2.4ghz), nRF24L01 (2.4ghz), Moteino RFM12B (915mhz), FS1000A (ASK 433mhz).  

## More Resources

RFM12B https://www.sparkfun.com/products/retired/12031  
nRF24L01 http://www.lydiard.plus.com/nrf24l01_1.htm  
Moteino Leo (Boards I have) - https://lowpowerlab.com/2013/04/24/moteino-leo-atmega32u4-based-moteino/  
ESP8266 Mesh Networking (painlessMesh) - https://github.com/gmag11/painlessMesh  
LoRa - There is a lot of information about LoRa - but don't confuse it with   LoRaWAN they really are two very different things.  
Some General Information can be found here: https://www.seeedstudio.com/RFM95-Ultra-long-Range-Transceiver-Module%2FLoRa-Module%2Fsupport-868M-frequency-p-2807.html  
FS1000A - There is also a lot of information about these - here is the library I used - https://github.com/madsci1016/Arduino-EasyTransfer  
Some more information, they are now using RadioHead Library but otherwise the information is good: https://microcontrollerelectronics.com/fs1000a-wireless-rf433-transmit-and-receive-module-pair/  


## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## Support Me

If you find this or any of my projects useful or enjoyable please support me.  
Anything I do get goes to buy more parts and make more/better projects.  
https://www.patreon.com/kd8bxp  
https://ko-fi.com/lfmiller  

## Other Projects

https://www.youtube.com/channel/UCP6Vh4hfyJF288MTaRAF36w  
https://kd8bxp.blogspot.com/  


## Credits

Copyright (c) 2018 LeRoy Miller

## License

This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses>
