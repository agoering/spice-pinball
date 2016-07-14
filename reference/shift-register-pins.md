---
layout: reference
title: Shift Register Pinout
collection: reference
prev_section: sketch-guide
next_section: motorcontroller
permalink: /reference/shift-register-pins/
---

### Shift Register Pinout

The pinout for the shift register can be confusing. Here's how to connect it:

- Data: to Arduino pin 14
- Latch: to Arduino pin 12
- Clock: to Arduino pin 11

Additionally, do the following:

- Ground shift register pins 8 and 13
- Connect shift register pins 10 and 16 to +5V
- With multiple shift registers, connect pin 9 of one shift register to the next shift register's data pin (pin 14).

<img src="http://bildr.org/blog/wp-content/uploads/2011/02/574px-SN74HC595-pinout.png" style="width: 200px"/>