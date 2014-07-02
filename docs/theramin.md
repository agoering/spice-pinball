---
layout: docs
title: RGB Theramin
prev_section: maketones
next_section: sessionc
permalink: /docs/theramin/
--- 

Since speakerValue will be between 100 and 1023, we can use ```tone()``` to write directly to the speaker. We do that like so:

```tone(speakerPin,speakerValue,100);
```

That writes ```speakerValue``` to ```speakerPin``` for ```100``` milliseconds.

Ok, let's have fun! Plug pin 8 from Arduino to the free leg of the pin (the one that's not grounded). And have fun with your RGB theramin!

