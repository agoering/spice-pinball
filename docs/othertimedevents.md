---
layout: docs
title: Other timed events
prev_section: timedloopedevent
next_section: multiplexers
permalink: /docs/othertimedevents/
---

Now we'll see another use of the timed events object. Disconnect the
green LED from the arduino, and reconnect the first shift register's
data pin to the arduino's pin 11. Now upload:

<a href="/sketches/s2_sh03c.txt">s2_sh03c</a>


Now the timed event is being supplied the name of the function ```shiftpattern```.

Also, the value arrays ```values[]``` and ```val2[]``` are no longer
just ones and zeros. Try pressing the button.

**_CHECKPOINT!_**


The new looped sequence is defined in ```val2[]``` and ```tim2[]```,
and is of length 8.


- Try changing the order of numbers inside ```val2[]``` so the background loop has lit LEDs running away from each other instead of towards.
- Try extending the length of ```values[]``` and ```timing[]``` to trigger a more complicated timed sequence upon button press. You can use higher numbers than 9, and modify ```shiftpattern``` to respond with new patterns.

**_CHECKPOINT!_**

Note the ```shregs.update(serdata)``` is now being called inside
```shiftpattern()```.