---
layout: docs
title: Simple LED Circuit
prev_section: supplies-a
next_section: breadboards
permalink: /docs/simple-circuit/
---

Now that we have learned how to write programs to control the PBJ robot, the next step is to get familiar with how electrical circuits work. 

A **circuit** is a loop that allows electricity to ﬂow. The ﬂow of electricity is called **current**. Current is pushed through a circuit by differences in **voltage**.

The most important fact you need to know is this:

**_Current flows from higher voltage to lower voltage._**

You may have heard the words "current" and "voltage" before. Perhaps you have seen the word "volts" printed onto batteries.

When an electrical circuit is connected to both ends of a battery,
then current will flow through the circuit from the higher voltage end of the battery (indicated by +) to the lower voltage end (indicated by -). 

It may help to think about current as a fluid that flows from positive to negative. 

To understand this better, let's study a simple component:

<img src="https://learn.adafruit.com/system/assets/assets/000/002/159/large1024/learn_arduino_red_led_5mm_cropped.jpg?1396780038" style="width: 650px"/>

The red bulb-like component is called an LED, which is short for
"Light Emitting Diode". An LED will glow if a current passes through
it. But LEDs are special, in that the current needs to flow only in
one direction (into the long leg (+) and out of the short leg (-)) for it to work. Trying to force current into the short leg will blow up the LED. LEDs don’t like that.

So, can we just connect the long leg to the (+) side of a battery and the short leg to (-)? **NO WAY!!!** LEDs can get damaged if too much current flows through them. To decrease the amount of current that flows in a circuit, we use resistors. They look like this:

<img src="https://learn.adafruit.com/system/assets/assets/000/002/160/large1024/learn_arduino_R-270-level.jpg?1396780043" style="width: 650px"/>

The colored stripes are a code that indicate the size of the resistor. Resistors with a larger value reduce current more than resistors with a smaller value. 

Therefore, to make an LED glow, we must connect to it through a resistor to a battery. Since we can't just hold these things in place, we're going to use breadboards to make connections from component to component. Also, instead of batteries, we've set up power sources right on the breadboards. That's what the next page is all about! 

