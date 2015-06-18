---
layout: docs
title: Supplies
prev_section: pinball-sounds-exercise
next_section: shiftregisters
permalink: /docs/supplies-c/
---

Today we will learn to use a special chip that will be helpful in making our pinball machines. Also, today's setup can be used directly as a model for how to read many inputs and write to many outputs - and it can be used with a few modifications as a direct model for the pinball electronics that you will build.

- Breadboard with the same setup as the Sounds and Senses:
    - Power supply
    - Arduino
    - 4x momentary switches
    - 1x buzzer or  computer speaker
    - 1x NPN transistor
    - 1x green LED
    - 1x 1k resistor for green LED
    - 1x 200 ohm resistor for transistor base
    - 2x shift registers
    - 8x red LEDs
    - 8x blue LEDs
    - 16x 10k resistors for shift register LEDs

- Sensor Kit:
    - 1x infrared emitter/receiver, pre-soldered to resistors
    - 1x large momentary switch
    - 1x piezo sensor
    - 1x 1M resistor to read piezo (connect in parallel)
    - 1x force sensitive resistor
    - 1x 10k resistor for FSR (connect as voltage divider, FSR high)

Additionally, every table must have received a SPICE scoreboard.

The breadboard should look like this:

<img src="{{ site.baseurl }}/img/b-breadboard.jpg" style="width: 650px"/>

And the scoreboard like this:

<img src="{{ site.baseurl }}/img/scoreboard-front.png" style="width: 500px"/>

For the first bit, we will focus on this part of the breadboard:

<img src="{{ site.baseurl }}/img/c-shiftreg-led-area-2.png" style="width: 300px"/>


