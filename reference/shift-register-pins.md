---
layout: reference
title: Shift Register Pinout
collection: reference
prev_section: reference-main
next_section: current-budget
permalink: /reference/shift-register-pins/
---

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

<img src="http://bildr.org/blog/wp-content/uploads/2011/02/574px-SN74HC595-pinout.png" style="width: 500px"/>

SER: Set Value for Leftmost “Chair”
SRCLK (Clock) High: Move Over! (shift in the next bit)
RCLK (Latch) High: Display new settings
OE: When Low, enable outputs (so pull low)
SRCLR (Clear): When Low, Clear stored data (so pull high).

If you want, you can do this without a microcontroller by setting up some control buttons. Basic tact switch setup: one leg goes high and the other goes through a 1k resistor to gnd. Then put the leg connected to GND so that it sends low to SER when not pushed and sends high to SER when pushed. Test this on an LED first. Set up three of these, test each, and connect to SER, SRCLK, and RCLK. 

See more <a href="http://hackaday.com/2013/02/07/learn-shift-registers-without-involving-a-microcontroller/">here</a> and <a href="http://www.learningaboutelectronics.com/Articles/Shift-register-circuit.php">here.</a>