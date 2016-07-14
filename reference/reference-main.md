---
layout: reference
title: Quick References
prev_section: 
next_section: sketch-guide
permalink: /reference/main/
---

This guide is for you! If you find yourself wishing for quick access to a snippet of code, a circuit layout example, or anything else, let us know on our <a href="https://docs.google.com/forms/d/1CZS4cuOhvA9gaFyjlWKAAf6xRf0unapmy681tcqHq-M/viewform?usp=send_form" target="_blank">suggestion form</a> and we will add it to this page! For now, please enjoy this awesome poster by <a href="cbrewste@uoregon.edu">Carolyn Brewster</a> which outlines the most important circuit elements!

<img src="{{site.baseurl}}/img/SPICE-poster.png" style="width: 500px"/>

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

<img src="http://bildr.org/blog/wp-content/uploads/2011/02/574px-SN74HC595-pinout.png" style="width: 200px"/>

## A word on Arduino pins

> Arduino Nano pins A0, A1, A2, A3, A4, and A5 can actually be used as digital
I/O pins 14, 15, 16, 17, 18, and 19. The other analog pins A6 and A7 can only be used as analog inputs.