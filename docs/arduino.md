---
layout: docs
title: Arduino time!
prev_section: transistors
next_section: programs
permalink: /docs/arduino/
---

Now, we are ready to control our electronics using a microcontroller
robot. The microcontroller we will be using is called an Arduino Nano.

<img src="http://upload.wikimedia.org/wikipedia/commons/8/8d/Arduino_Nano.jpg" style="width: 500px"/>

<img src="{{ site.baseurl }}/img/nano3_pinouts.png" style="width: 500px"/>

Look at the Arduino on your breadboard closely. The most important things
to look for right now are the USB connector and the pin
numbers. Those holes/sockets on the breadboard next to the numbers
are what we are going to use to connect the Arduino to our electrical
circuits.

In the programs, we will refer to pins by their name. The pins "A0" through "A7" can be referred to exactly that way, while the pins "D2" through "D13" are simply referred to as "2" through "13". 

Let's program the Arduino! To do this, first connect the Arduino
to your computer using the USB cable.
Then launch the Arduino programmer by clicking on this icon:

<img src="{{ site.baseurl }}/img/arduino-icon.png" style="width: 200px"/>

You should see a window open that looks like this:

<img src="{{ site.baseurl }}/img/arduino-window.png" style="width: 500px"/>

This blank white space is where we can write our programs. But before
we do that, let us connect our Arduino to the first circuit we played
with. 

First, notice that the pins labeled **Vin** and **GND** are already connected to 5V and ground, respectively. This will always be the case; don't remove those connections.

Disconnect the wire from the transistor base that you previously connected to the red-line 5V row, and instead connect it to the Arduino pin labeled 12. 

<img src="{{ site.baseurl }}/img/a-arduino-led-circuit.jpg" style="width: 650px"/>

**_CHECKPOINT!_**

Nothing is happening to the LED, because we have yet to tell (program) the Arduino to do anything!



