---
layout: docs
title: Piezo Sensor
prev_section: proximity-sensor
next_section: force-sensitive-resistor
permalink: /docs/piezo-sensor/
---


Another kind of analog input we'll use is a piezoelectric (piezo) sensor. It is made of a material that generates a voltage when it is physically deformed via a mechanical force or vibration (including sound vibrations). It can also be used in the reverse, to produce a tone when a voltage is placed across it (this is how piezo buzzers or speakers work!) 

Piezos, like LEDs are polarized, so it is important to always connect the red wire to high and the black wire to ground. We will use a resistor in parallel with the piezo to reduce the amount of voltage and current produced, in order to protect the analog input. 

Here is how we connect the piezo:

<img src="{{ site.baseurl }}/img/piezo-connection.jpg" style="width: 650px"/>

The signal produced by the piezo is larger for harder presses. It can also detect banging or knocking on the surface on which it sits, and how sensitive it will be will depend on the resistor used to read it. This will be most effective if the piezo is taped to or otherwise firmly held in contact with a surface. 

Since it's large and flat, it's a great choice for measuring something rolling over it, and it's good at picking up fast events. It's not as good for measuring longer events, as you will see in today's session.