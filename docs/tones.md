---
layout: docs
title: Producing Tones
prev_section: analog-ranges
next_section: scoreboard
permalink: /docs/tones/
--- 

Up to now we have only controlled lights. Now let's make some sounds! Each group has a speaker. The paper cone of the speaker is attached to a magnet which vibrates when electrical signals are sent to the speaker wires, producing sound. Vibrating the cone at different frequencies produces different tones.

Connect one end of your speaker to the capacitor on the amplifier circuit. Connect the other end to ground through the lonely blue resistor on your board under the buttons. 

We are going to use a function called ```tone()``` to produce tones. If you use this function, you should know that it prevents the use of pins 11 and 3 as analog outputs. 

Open the **tones** sketch and look at the code just under the ```map()``` function code block. You'll see the following:


```speakerVal = map(piezo_val, piezo_thresh, piezo_max, 33, 4186);

if (piezo_val > piezo_thresh){
  tone(speakerPin,speakerVal,1000); 
}
```

In the first line, we're using the ```map()``` function to convert the sensor value to tone values the speaker can use. In the ```if()``` statement, we use ```tone()``` to write ```speakerValue``` to ```speakerPin``` for ```1000``` milliseconds, but only if the value is above the piezo threshold (without this, the speaker plays constantly and is very annoying!).

The ```tone()``` function can produce specific musical notes. You will explore that more in another activity. For now, we need to know only that ```tone()``` can produce outputs ranging from 31Hz to 4978Hz (those are units of frequency called Hertz). What are the lowest and highest values the value of ```speakerValue``` can be, given that the analog inputs can only go from 0-1023? What will that value depend on? Does this range fit into the range used by ```tone()```? Does it fill the range fully, over fill, or fill it incompletely?

Now upload the sketch and interact with the piezo. Try adjusting the threshold values for the piezo, or the values used in the ```map()``` function and see how that changes the tones that you can produce.

**_CHECKPOINT!_**