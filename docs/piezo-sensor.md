---
layout: docs
title: Piezo Sensor
prev_section: analoginputs
next_section: serial-monitor
permalink: /docs/piezo-sensor/
---

The analog sensor we'll use is called a piezoelectric (piezo) sensor. It is made of a material that generates a voltage when it is physically deformed via a mechanical vibration (including sound vibrations). It can also be used in the reverse, to produce a tone when a voltage is placed across it (this is how piezo buzzers or speakers work!) 

Piezos are polarized (like LEDs), so it is important to connect the red wire to high and the black wire to ground. We will use a resistor in parallel with the piezo to reduce the amount of voltage and current produced, in order to protect the analog input. 

To connect the piezo, make sure the red and black wires from the piezo are connected to opposite sides of the resistor with brown, black and green stripes. Make sure the black wire side also has a connection to ground, and that the red wire side also has a connection to pin A1 on the Arduino:

<img src="{{ site.baseurl }}/img/piezo-connection.jpg" style="width: 650px"/>

The signal produced by the piezo is larger for harder taps. It can also detect banging or knocking on the surface on which it sits, and how sensitive it will be will depend on the resistor used to read it, how hard the surface it is mounted on is, and how firmly it is mounted to that surface. Piezos will be most effective when firmly held in contact with a surface. This can be done by adhering it tightly to that surface, or by sandwiching it between a surface and a small weight.

The piezo requires a _vibration_ to sense a signal - it will not respond to a steady constant force.  - there needs to be a vibration generated. Piezos are very good at picking up fast events that generate quick taps or knocks, which makes them a good choice for a sensor in a fast-moving pinball game. 

Piezos can be used one of two ways: direct or indirect events. A direct contact event would be like a pinball rolling quickly over the piezo. An example of an indirect event would be a collision with an object that the piezo is mounted to (so that the piezo itself is never actually touched). One problem with using piezos for direct contact events is that you must be careful not to knock the wires off of the piezo. The solder connections to the wires are very delicate and the piezo will no longer work if the wires are shorn off!