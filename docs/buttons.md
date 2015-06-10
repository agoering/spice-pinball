---
layout: docs
title: Buttons
prev_section: two-leds
next_section: delay-trouble
permalink: /docs/buttons/
---

Now that we know how to make LEDs blink at definite times, we will learn how to turn LEDs on and off using a button. Connect one of
the buttons in the breadboard to pin 10 of the Arduino as shown:

<img src="{{ site.baseurl }}/img/a-buttons.png" style="width: 650px">

Now upload the following program:

<a href="{{ site.baseurl }}/sketches/04_button1.txt">04_button1</a>

Press the button to control the LED on pin 12.

Now, let us look at what new lines and words are in the program.
The ```setup()``` function has the following two lines:

```pinMode(buttonpin, INPUT); 
digitalWrite(buttonpin, 1);
```

These two lines tell the Arduino that pin 10 (or whatever the value of the ```buttonpin``` variable is) will be used to measure voltages, instead of putting out voltages.

Inside the ```loop()``` function, there is a new structure:

```if ( CONDITION ) {
    DO ONE THING
}
else {
  DO THE OTHER THING
}
```

This **if-else** structure is used to do conditional logic. The
condition is put inside the normal brackets right next to ```if```. For example, in this program, the ```CONDITION``` was:

```digitalRead(buttonpin) == LOW
```

which is to read the voltage on pin 10 (buttonpin) and check if it is
low. Everytime the voltage is measured to be low (whenever the button
is pressed), the lines in the ```DO ONE THING``` space will be executed. If the ```CONDITION``` is not met, then the lines on  ```DO THE OTHER THING``` will be used.

The double equals sign ```==``` is important for ```CONDITIONS```.

Try the following modifications:

1.  Try making the LED turn on when the button is NOT pressed, and turn off when the button IS pressed.
2.  Try adding lines to the program so that the LED in pin 11 blinks
once every second while the button still controls the LED on pin 12.

Is the second modification working? What do you think the main problem is? Remember, the Arduino goes to sleep during the ```delay()``` call.

**_CHECKPOINT!_**

