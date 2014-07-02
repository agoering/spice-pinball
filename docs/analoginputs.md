---
layout: docs
title: Analog Inputs
prev_section: supplies-b
next_section: readsensors
permalink: /docs/analoginputs/
---

So far we have dealt only with digital inputs, which have two values: off and on, or 0 and 1. There's another class of inputs - **analog** inputs have a smooth range between two values - "off" and "full blast."  A simple kind of analog control you are familiar with is a volume knob on a radio. A dimmer switch on household lights is another example.

The kind of analog input we'll use in this activity is a proximity sensor. It is made of an infrared emitter and receiver, pointing in the same direction, with a wall between them. The emitter creates pulses of infrared light. When this infrared light reflects off of surfaces (your hand, a pinball), it is sent back to the receiver, which produces a small voltage. The resistors soldered to the setup are arranged such that the output signal read on the green wire is between 5V and 0V. The red wire on the sensor will connect to 5V, and the black wire to 0V.

<img src="/img/proximity_sensors.png" style:"width: 650px"/>

The signal produced by the proximity sensor is largest (near 5V) for objects held near the detector, and falls off to 0V as objects are moved farther away. 

