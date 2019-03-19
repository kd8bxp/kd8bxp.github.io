# Bitty Bot

Testing Library for Bitty Bot Rover.
Version 2 of a Bitty Bot Motor Library, not working correctly.
For something that is working, that this library was based from see the testing-class branch of this 
repository.
Updated for testing Sept 4, 2016

## Installation

TODO: Describe the installation process

## Usage

Put BittyBot folder in your libraries directory, restart the IDE, and test it out. 

A number of changes have happened to update the library: 

include "BittyBot2.h"

create a BittyBot object -

BittyBot BittyBot2(PWMLPin, PWMRPin, L1Pin, L2Pin, L3Pin, L4Pin);

BittyBot.begin(); // This setups the pins for output, it sets a speed of zero, and sets the drive pins to low, and calibrates the wheels to the magnetic sensor 
BittyBot.Speed(LeftSpeed, RightSpeed);
BittyBot.update(); //checks to see if motors have been running for a specific time period. Time is passed with the movement commands
BittyBot.leftTight(time);  //turn in place to the left
BittyBot.rightTight(time); //turn in place to the right
BittyBot.left(time);   //turn left going forward
BittyBot.stop(); //stop all motors and pwm. No delay 
BittyBot.right(time); //turn right going forward
BittyBot.forward(time); //move the robot forward
BittyBot.back(time); // move the robot backward
BittyBot.IsRunning(); //returns a 1 if the motors should be on and running, and a zero if they should be off and stopped.  This can be used for loops, or for checks to see if it really is moving
BittyBot.calibrate(); //used by the begin sub-routine, could be used to reset the wheels if you think they have gotten too far from each other. Does not reset the drive pins to low, so a stop just after might be needed.

See Library Sketch for some examples.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## Credits

LeRoy Miller

This is my very 2nd Arduino Library, it was not as easy to convert the class sketch to a library, and this library is currently broken.
Oct 3, 2015

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
    along with this program.  If not, see <http://www.gnu.org/licenses
