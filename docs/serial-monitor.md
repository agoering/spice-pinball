---
layout: docs
title: The Serial Monitor
prev_section: delay-trouble
next_section: rgb-led
permalink: /docs/serial-monitor/
---

There are some other lines in the **stopwatch** program that we need to explain. Inside ```setup()```, there is a line that says ```Serial.begin(9600)```.

This is opening a channel between the computer and the Arduino so they can speak to each other while the program is running.

In the Arduino window, there is a button to the top-right that opens the serial monitor. Click on it:

<img src="{{ site.baseurl }}/img/serial-monitor.png" style="width: 650px"/>

What does the  serial monitor window say? Compare the timing of it
with the blinking LED.

Further down in the program, inside the LED blinking ```if``` structure,
there are these two lines:

```Serial.print("led state is ");
Serial.println(ledbstate);
```

This is controlling what the Serial monitor says.  The ```Serial.print()``` function causes the Arduino to print anything that you put inside the brackets onto the serial monitor.  The ```Serial.println()``` function does the same, but also goes to the next line. 

Try the following modifications:

1. Change the ```println``` to ```print``` and upload. What did this change?
2. Change it back to ```println```, but now change the text "led state is" to something else. Did your changes take effect?
3. Make the pin 11 LED blink slower. Check if this slows down the
serial stuff as well.

**_CHECKPOINT!_**

The serial monitor is helpful in debugging Arduino code, but it has
two disadvantages:

1. It uses up pins TX1 and RX0, so you can't use those for anything else
if you are using ```Serial.begin(9600)```. Otherwise, you could use them as digital pins (like D2 through D13). 
2. It can slow your code down.

In the final Pinball program, it is generally a good idea not to use
them. One good way of keeping the lines inside the program but not
uploading it into the microcontroller is to 'comment' the lines out.

To do this, add a ```//``` before those lines. You can also select a block and go to ```Edit > Comment/Uncomment``` to do several lines at once. Change all the three Serial lines to:

```//Serial.begin(9600);
//Serial.print("led state is ");
//Serial.println(ledbstate);
```

Now those lines should turn grey. Try uploading the program now, and
checking the serial monitor.

The serial monitor now shows nothing. This is because those lines were skipped when the computer uploaded your program into the Arduino. You can bring them back into the program anytime by removing the ```//``` symbol. You can also use the ```//``` symbol to put helpful comments in English for you (and others) to understand your program better. We will do this from the next program onwards.

