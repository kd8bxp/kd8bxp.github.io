#Arduino Blink

Why is important to blink a LED?

- It shows how digital IO works.

```
void setup() {

    pinMode(13, OUTPUT);

}

void loop() {

    digitalWrite(13, HIGH);
    delay(1000);
    digitalWrite(13, LOW);
    delay(1000);

}
```

In the above example, we set the LED pin to be a OUTPUT - This tells the microcontroller that whatever is connected to the pin is expecting something
from the controller.  A INPUT would tell the microcontroll to expect to see something (data) on that pin.  
Inside the loop we tell PIN 13 to go HIGH, delay for 1000 microseconds (about 1 second.) and go LOW, delay again, and repeat. In this case a HIGH will turn the LED on and a LOW will turn it off.  The delay will STOP the microcontroller from doing anything else.  
The the controller is delayed it can not do anything else (mostly), no other sensors can be used, or outputs have information written to them.

Is there a better way?

#Blink without delay

The delay() function is blocking, so what if we need to do something else and still blink a led.

We can use a method like below, this allows the sketch to continue to run and still processes the blink code, about once a second.

```
// Variables will change:
int ledState = LOW;             // ledState used to set the LED

// Generally, you should use "unsigned long" for variables that hold time
// The value will quickly become too large for an int to store
unsigned long previousMillis = 0;        // will store last time LED was updated

// constants won't change:
const long interval = 1000;           // interval at which to blink (milliseconds)

void setup() {
  // set the digital pin as output:
  pinMode(13, OUTPUT);
}

void loop() {
  // here is where you'd put code that needs to be running all the time.

  // check to see if it's time to blink the LED; that is, if the difference
  // between the current time and last time you blinked the LED is bigger than
  // the interval at which you want to blink the LED.
  unsigned long currentMillis = millis();

  if (currentMillis - previousMillis >= interval) {
    // save the last time you blinked the LED
    previousMillis = currentMillis;

    // if the LED is off turn it on and vice-versa:
    if (ledState == LOW) {
      ledState = HIGH;
    } else {
      ledState = LOW;
    }

    // set the LED with the ledState of the variable:
    digitalWrite(13, ledState);
  }
}
```


