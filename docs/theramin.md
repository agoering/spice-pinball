---
layout: docs
title: RGB Theramin
prev_section: 
next_section: 
permalink: /docs/theramin/
--- 

Since speakerValue will be between 100 and 1023, we can use ```tone()``` to write directly to the speaker, like so:

```tone(speakerPin,speakerValue,100);
```

That writes ```speakerValue``` to ```speakerPin``` for ```100``` milliseconds.

Ok, let's have fun! 

First you will need to uncomment (delete the ```//``` marks) the line that says ```tone(speakerPin,speakerValue,100);```. Then connect Arduino pin 8 to the free leg of the speaker (the leg that's not grounded). If you've moved your board around, you may need to recalibrate your sensors again to optimize your theramin. 

Have fun with your RGB theramin!

**_CHECKPOINT!_**