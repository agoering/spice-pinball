---
layout: docs
title: Producing Tones
prev_section: analog-as-digital
next_section: analog-ranges
permalink: /docs/analog-tones/
--- 

Up to now we have only controlled lights. Now let's make some sounds! Each group has a piezoelectric speaker. A sheet of metal attached to a magnet inside the speaker vibrates when electrical signals are sent to the speaker wires, producing sound. Vibrating the sheet of metal at different frequencies produces different tones.

Connect one end of your speaker to Arduino output in D3. Connect the other end to ground through the lonely blue resistor on your board under the buttons. 

We are going to use a function called ```tone()``` to produce tones. If you use this function, you should know that it prevents the use of pins 11 and 3 as analog outputs. 

Open the **analog-tones** sketch and look at the code just under the ```map()``` function code block. You'll see the following:


```speakerValue = (sensorValue0+sensorValue1+sensorValue2);

if (speakerVal > Min0 + Min1 + Min2 ){
  tone(speakerPin,speakerVal,100); 
}
```


In the first line, we're adding up the sensor values to write to the speaker. In the ```if()``` statement, we use ```tone()``` to write ```speakerValue``` to ```speakerPin``` for ```100``` milliseconds, but only if the value is above the minimum set for all of the sensors (without this, the speaker plays constantly and is very annoying!).

The ```tone()``` function can produce specific musical notes. You will explore that more in the next page. For now, we need to know only that ```tone()``` can produce outputs ranging from 31Hz to 4978Hz (those are units of frequency called Hertz). What are the lowest and highest values the value of ```speakerValue``` can be, given that the analog inputs can only go from 0-1023? What will that value depend on? Does this range fit into the range used by ```tone()```? Does it fill the range fully, over fill, or fill it incompletely?

Now upload the sketch and interact with the analog sensors. Try the following modifications (remember to save as **analog-tones-mod** in your **Mod** folder!):

1. Combine elements from the **analog-tones** and **analog-digital** sketches to play tones on the speaker, but only when one input is used as a button. For example, use the piezo as a button and use the FSR and proximity sensor to produce the tone. 

**_CHECKPOINT!_**