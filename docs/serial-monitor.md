---
layout: docs
title: The Serial Monitor
prev_section: piezo-sensor
next_section: readsensors
permalink: /docs/serial-monitor/
---

One last task before we start reading sensors! 

Make sure the piezo has been set up as described in the previous page. 

Plug in your breadboard, then connect your Arduino to the computer. Connect the base of the transistor connected to the green LED to Arduino pin D2. Open the Arduino program:

<img src="{{ site.baseurl }}/img/arduino-icon.png" style="width: 200px"/>

Upload the **analog-thresholds** sketch from the **Sounds and Senses** sketchbook. 

Note that inside ```setup()``` is the line ```Serial.begin(9600)```. This is setting up a channel between the computer and the Arduino so they can speak to each other while the program is running. Using the **serial monitor**, we can watch the sensor values in real time. 

In the Arduino window, there is a button to the top-right that opens the serial monitor. Click on it:

<img src="{{ site.baseurl }}/img/serial-monitor.png" style="width: 650px"/>

Notice that a string of numbers is being written out, corresponding to the analog input. Tap on the piezo. What happens to the Serial Monitor display and LED as you do so?

The numbers on the serial monitor tend to move fast! You can deselect "auto-scroll" on the serial monitor to stop the scrolling to look at specific readings.

Inside the ```loop()```, we write a value to the Serial Monitor using the line ```Serial.println(piezo_val);``` This is controlling what the Serial monitor says. Find one of those lines now. 

The ```Serial.println()``` function causes the Arduino to print anything that you put inside the parentheses onto the serial monitor, and places each reading on a new line. You can also print on the same line by using ```Serial.print()``` without the ```ln```.  

The serial monitor is helpful in debugging Arduino code, but it has
two disadvantages:

1. It uses up pins TX1 and RX0, so you can't use those for anything else
if you are using ```Serial.begin(9600)```. Otherwise, you could use them as digital pins (like D2 through D13). 
2. It can slow your code down.

In the final Pinball program, it is generally a good idea not to use
them. One good way of keeping the lines inside the program but not
uploading it into the microcontroller is to 'comment' the lines out.

To do this, add a ```//``` before those lines. You can also select a block and go to ```Edit > Comment/Uncomment``` to do several lines at once. Change the serial lines in each case to:

```
//Serial.println(piezo_val);
```

Now that line should turn grey. Try uploading the program now, and
check the serial monitor.

The serial monitor now shows nothing. This is because those lines were skipped when the computer uploaded your program into the Arduino. You can bring them back into the program anytime by removing the ```//``` symbol. 

