---
layout: docs
title: Shift Registers
prev_section: supplies-c
next_section: washiftregsdo 
permalink: /docs/shiftregisters/
---

One of the biggest problems you will encounter when making a pinball
machine is the limited number of pins on the arduino. The arduino has
only 13 digital pins (actually, it has 19, but we'll get to that
later). If you start to use Serial communications, then pin 0 and 1
cannot be used for anything else, leaving you with 11 digital pins.

Suppose I asked you to independently control 16 LEDs with one
arduino. How would you do this?
Why, by using shift registers of course!

Connect the following segments on the breadboard to pins 13, 12 and 11
on the arduino as shown:

PICTURE WITH PIN CONNECTIONS
<img src="/img/wes.png" style:"width: 650px"/>

Also connect the 0 volts line to arduino's GND pin.
Now upload this program:

<a href="/sketches/s2_sh01.txt">s2_sh01</a>

Power the Breadboard, and watch the 8 red LEDs.

**_CHECKPOINT!_**


