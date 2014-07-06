---
layout: docs
title: Producing Tones
prev_section: controloutputs
next_section: theramin
permalink: /docs/maketones/
--- 

Up to now we have only controlled lights. Now let's make some sounds! That round thing on the breadboard is a piezoelectric speaker. A sheet of metal attached to a magnet inside the speaker vibrates when electrical signals are sent to the speaker wires, producing sound. Vibrating the sheet of metal at different frequencies produces different tones.

<img src="{{ site.baseurl }}/img/speaker_closeup.png" style="width: 200px"/>

The speaker is very simple - one end connects to ground, and the other to an Arduino output pin.

We are going to use a built-in function called ```tone()``` to produce tones. If you use this function, you should know that it prevents the use of pins 11 and 3 as analog outputs. For example, we can't use those pins to control the RGB LED when we're using the ```tone()``` function. That's why we're using pins 10, 9, and 6 instead of 11, 10, and 9!

Before we connect the speaker, let's look at the code. Look just under the ```map()``` function code block. You'll see the following:

```speakerValue = (sensorValue0+sensorValue1+sensorValue2)/3;
```

Currently we are using three inputs to control three outputs (the red, green, and blue LEDs). However, the speaker only has a single input. Therefore, we're taking an average of the sensor values to write to the speaker. 

The ```tone()``` function can write to specific notes. You will explore that more later. For now, we need to know only that ```tone()``` can produce outputs ranging from 31Hz to 4978Hz (those are units of frequency called Hertz). What are the lowest and highest values the value of ```speakerValue``` can be? What will that value depend on? Do those fit into the range produced by ```tone()```?

**_CHECKPOINT!_**