---
layout: reference
title: Proximity Sensor
prev_section: sketch-guide
next_section: force-sensitive-resistor
permalink: /reference/proximity-sensor/
---


One kind of analog input we'll use in this activity is a proximity sensor. It is made of an infrared emitter and receiver, pointing in the same direction, with a wall between them. It looks like this: 

<img src="{{ site.baseurl }}/img/proximity-sensor-closeup.png" style="width: 650px"/>


The emitter creates pulses of infrared light. When this infrared light reflects off of surfaces (your hand, a pinball), it is sent back to the receiver, which produces a small voltage. The resistors soldered to the setup are arranged such that the output signal read on the green wire is between 5V and 0V. The red wire on the sensor will connect to 5V, and the black wire to 0V.

<img src="{{ site.baseurl }}/img/proximity-sensor-zoomout.png" style="width: 650px"/>

This sensor is very easy to set up. First, make sure the red and black wires from the proximity (infrared) sensor goes to +5V and ground. Connect the green wire to an analog input on the Arduino. 

<img src="{{ site.baseurl }}/img/proximity-connection.jpg" style="width: 650px"/>

The signal produced by the proximity sensor is largest (near 5V) for objects held near the detector, and falls off to 0V as objects are moved farther away. 

