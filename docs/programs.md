---
layout: docs
title: Using Arduino programs
prev_section: arduino
next_section: blink
permalink: /docs/programs/
---

Now, connect the power supply to the breadboard.
Nothing should happen, because we have yet to tell (program) the Arduino to do anything!

This session will use a lot of programs. But since this is your first
time programming an Arduino, we have pre-written most of the programs
for you. All you have to do is copy them and paste them into the white blank space in the Arduino window, and upload that program into the microcontroller. Let us try this with a simple program. Open this link in a new tab:

<a href="/sketches/01_blink.txt">01_blink</a>

Now copy everything in it and paste
it into the Arduino window. Then click on this button:

<img src="/img/arduino-upload.png" style="width: 650px"/>

Now look at the LED. It should be blinking!

**_CHECKPOINT!_**

Now we will control the transistor circuit instead. Disconnect the
Base of the transistor from 5 Volts, and instead plug it to Arduino
pin 12. Is the second LED blinking?

Now we can learn why we need transistors. 

The program you loaded into
the Arduino told it to make the voltage on pin 12 go UP and DOWN, UP
and DOWN, repeatedly once every second. This is why the LED
blinks. But when you connected the first circuit, all the current that was flowing through the LED came from the Arduino. When you connected the transistor circuit, all the current came from the wall power supply. (The base of the transistor does not consume very much current.)

<img src="/img/bad-good.png" style="width: 650px"/>

One must avoid having too much current flow through the Arduino, as
that can damage it. It is always better to use the transistor instead, and only use the Arduino to control the Base voltage.
