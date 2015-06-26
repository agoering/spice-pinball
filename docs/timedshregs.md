---
layout: docs
title: Timed Shift Registers
prev_section: timedloopedevent
next_section: fancyresetpattern
permalink: /docs/timedshregs/
---

Now let's see how to use timed events and shift registers together. Disconnect the
green LED from the Arduino, and reconnect the first shift register's
data pin to the Arduino's pin 10. 

Now upload the **timed-shift-pattern** sketch.

Now the timed event is being supplied the name of the function ```shiftpattern```.

Also, the value arrays ```values[]``` and ```val2[]``` are no longer
just ones and zeros. Try pressing the button.

**_CHECKPOINT!_**

The new looped sequence is defined in ```val2[]``` and ```tim2[]```,
and is of length 8. Here are a few modifications to make (make sure to save as **timed-shift-pattern-mod** in your **Mods** folder!)

- Try changing the order of numbers inside ```val2[]``` so the background loop has lit LEDs running away from each other instead of towards each other. This should be way easier to do than in the **two-shreg** sketch.
- Try extending the length of ```values[]``` and ```timing[]``` to trigger a more complicated timed sequence upon button press. You can use higher numbers than 9, and modify ```shiftpattern``` to respond with new patterns.

**_CHECKPOINT!_**

Note the ```shregs.update(serdata)``` is now being called inside
```shiftpattern()```.