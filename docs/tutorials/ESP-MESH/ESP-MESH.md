#ESP-MESH Board


This board isn't listed on the WIKI. Here is what I learned so far. (2/19/2019).  


1. Select Generic ESP8285 from the Arduino Boards manager.  
2. As the IDE is compiling the sketch, hold the flash button, release it when the IDE is waiting for the board.  
3. The RGB LED on board  
       1. RED is pin 12  
       2. BLUE is pin 13  
       3. GREEN is pin 14  
       4. digitalWrite HIGH will turn the LED off  
       5. digitalWrite LOW will turn the LED on  
       6. analogWrite (PWM) works from 0 to 1024.  
4. [PainlessMesh](https://gitlab.com/painlessMesh/painlessMesh) for the ESP8266/ESP32 board work with no problems.  
5. The "HelloMesh" example included with the ESP8266 boards also works, but you have to remember to set an IP address for each node.  

