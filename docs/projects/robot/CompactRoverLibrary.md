# BittyBot Compact Rover

Library for the BittyBot Compact Rover.
Mar 17, 2017 Copyright (C) LeRoy Miller
based on the BittyBot Library

## Installation

TODO: Describe the installation process

## Usage

Put CompactRover folder in your libraries directory, restart the IDE, and test it out. 

A number of changes have happened to update the library: 

include "CompactRover.h"

create a BittyBot object named bot

CompactRovert bot(LeftPin, LeftPWMPin, RightPin, RightPWMPin);

In void setup() put:
bot.begin(); // This setups the pins for output, it sets a speed of zero, and sets the drive pins to low


bot.update(); //checks to see if motors have been running for a specific time period. Time is passed with the movement commands, and should be called often while IsRunning flag is true.

bot.leftTight(time, PWMspeed);  //turn in place to the left
bot.rightTight(time, PWMspeed); //turn in place to the right
bot.left(time, PWMspeed);   //turn left going forward
bot.stop(); //stop all motors and pwm. No delay 
bot.right(time, PWMspeed); //turn right going forward
bot.forward(time, PWMspeed); //move the robot forward
bot.back(time, PWMspeed); // move the robot backward

bot.IsRunning(); //returns a 1 if the motors should be on and running, and a zero if they should be off and stopped.  This can be used for loops, or for checks to see if it really is moving

A few examples are included.

##Changes from BittyBot2 library

removed BittyBot.Speed(), removed BittyBot.calibration(), a number of changes
to the motor drive setup. CompactRover uses 4 wires for speed and direction, while BittyBot Rover uses 6 wires.
Some small code cleanup.

Sketches for BittyBot Rover should be easy to convert for the Compact Rover, with only a few minor changes in the code.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## Credits

Copyright (C) LeRoy Miller, Mar 17, 2017


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
