# I2C Communication Between two microcontrollers

This is an idea based on a comment made by Frank at our meeting on either Feb 15 or Feb 22.  
My first thoughts were to use the AT firmware for the ESP8266, after thinking about it I thought why not just use I2C.  

Problem is I didn't find a lot of examples for I2C communcation, a few old examples, and a few that didn't work well or explain what was going on.  
This is what I came up with based on a couple of the examples I did find.  
This is a demo of communication using the I2C bus between an Arduino Mega with MP3 shield, and a D1 Mini with 5 buttons.  By pushing the buttons the D1 Mini will tell the Mega which MP3 file to play.  

Whats not working - I can get the master (D1 Mini) to send a message to the  
slave device (MEGA/MP3 player).  I haven't figured out how to get the slave  
to send a status report back yet.  
This will have to be a demo for another time.  

## Documentation

https://docs.google.com/document/d/17qPdnuz_0vcQxwqyIxbd-e1VFhrlClPlq28MblpcvN0/edit?usp=sharing  

## Information

Based on code from: https://www.arduino.cc/en/Tutorial/MasterWriter  
and http://dsscircuits.com/articles/arduino-i2c-slave-guide  

## Usage

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
