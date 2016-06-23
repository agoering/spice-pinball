---
layout: reference
title: Motor Controller
collection: reference
prev_section: shift-register-pins
next_section: h-bridges
permalink: /docs/motorcontroller/
---

### Motor Controller Board Overview

You should have:

- a power supply breadboard (any of them will do)
- motors (CD drive and fan which we will scavenge from old computers)
- a motor control board, which looks like this:

<img src="{{ site.baseurl }}/img/d-motor-control.png" style="width: 500px"/>

The Arduino boards can only control a small amount of current. The motor controller boards are a handy device for controlling the larger currents that some devices such as motors need. Each motor controller board can drive two motors independently in either direction. 

Each motor controller board should have 10 wires:
- two power wires (red, black) for the chip
- two control wires (pair of yellow wires) for the first motor
- two control wires for the second motor
- two output wires (pair of blue wires) for the first motor
- two output wires for the second motor. 

The location of the wires is shown in the diagram below, but the leads should also be labelled appropriately.

You don't have to use both motors; just keep the unwanted control and output wires disconnected.


### How to Setup


1. To set up the motor controller board, we first need to connect the power lines (red/V++ and black/ground) to the breadboard.
2. Next, we hook up the control wires (yellow) to the Arduino output pins.
3. Finally we hook up our motors up to the green wires.

To test the motor, upload the example **Examples->SpicePinball->Pbmotorcontrol in the Arduino IDE**.



