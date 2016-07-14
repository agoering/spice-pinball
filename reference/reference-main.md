---
layout: reference
title: Quick References
prev_section: 
next_section: current-budget
permalink: /reference/main/
---

This guide is for you! If you find yourself wishing for quick access to a snippet of code, a circuit layout example, or anything else, let us know on our <a href="https://docs.google.com/forms/d/1CZS4cuOhvA9gaFyjlWKAAf6xRf0unapmy681tcqHq-M/viewform?usp=send_form" target="_blank">suggestion form</a> and we will add it to this page! For now, please enjoy this awesome poster by <a href="cbrewste@uoregon.edu">Carolyn Brewster</a> which outlines the most important circuit elements!

<img src="{{site.baseurl}}/img/SPICE-poster.png" style="width: 650px"/>

<!-- <img src="{{ site.baseurl }}/img/d-motor-control.png" style="width: 500px"/> -->

## Shift Register Pinout

The pinout for the shift register can be confusing. Here's how to connect it:

- Data: to Arduino pin 14
- Latch: to Arduino pin 12
- Clock: to Arduino pin 11

Additionally, do the following:

- Ground shift register pins 8 and 13
- Connect shift register pins 10 and 16 to +5V
- With multiple shift registers, connect pin 9 of one shift register to the next shift register's data pin (pin 14).

**Shift Register Musical Chair Analogy:**

<a href="http://bildr.org/2011/02/74hc595/">You can think of shift registers as "musical chairs."</a>

<img src="http://bildr.org/blog/wp-content/uploads/2011/02/574px-SN74HC595-pinout.png" style="width: 200px"/>

SER: Set Value for Leftmost “Chair”
SRCLK (Clock) High: Move Over! (shift in the next bit)
RCLK (Latch) High: Display new settings
OE: When Low, enable outputs (so pull low)
SRCLR (Clear): When Low, Clear stored data (so pull high).

If you want, you can do this without a microcontroller by setting up some control buttons. Basic tact switch setup: one leg goes high and the other goes through a 1k resistor to gnd. Then put the leg connected to GND so that it sends low to SER when not pushed and sends high to SER when pushed. Test this on an LED first. Set up three of these, test each, and connect to SER, SRCLK, and RCLK. 

See more <a href="http://hackaday.com/2013/02/07/learn-shift-registers-without-involving-a-microcontroller/">here</a> and <a href="http://www.learningaboutelectronics.com/Articles/Shift-register-circuit.php">here.</a>

## A word on Arduino pins

> Arduino Nano pins A0, A1, A2, A3, A4, and A5 can actually be used as digital
I/O pins 14, 15, 16, 17, 18, and 19. The other analog pins A6 and A7 can only be used as analog inputs.

## Speaker Amplification Circuit


A <a href="http://electronics.stackexchange.com/questions/129277/how-many-volts-can-a-1-watt-8-ohm-speaker-take">“Class A” amplifier arrangement</a> works well to keep a quiet speaker output for activities and prevent large current draw: 

<img src="http://i.stack.imgur.com/vxynt.png" style="width: 50px"/>

Without the capacitor, the setup is louder. R1 can be dropped down to 470Ohm (for a 10.6 mA draw). For the final machines, the speaker can most likely be used with a direct connection to pin 13 for highest volume. We haven't verified that this draws a safe current from that Arduino pin, but we haven't broken anything either!

