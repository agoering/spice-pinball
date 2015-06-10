---
layout: docs
title: Using the Reset pin
prev_section: external-power
next_section: supplies-b
permalink: /docs/reset-pattern-exercise/
---

Once we set Arduino free from the computer, it will simply run the last program that was uploaded. But what if you want to restart that program to the beginning? For example, in your pinball game, you might want to restart the program for every new game. We'll learn how to do that now.

Reconnect the Arduino to your computer via the USB cable. Open your **flags-mod** program, so we can use the cool pattern you created. 

Call this function inside the ```setup()``` function right before the ```makedark()``` function. Upload, and watch what happens. Try hitting the white reset button on the Arduino itself. When you do, the pattern from the function you put inside ```setup()``` should play once, and then it should return to the normal RGB control behavior.

Now disconnect the USB cable from the computer. Disconnect the switch
from pin 8, and instead connect it to the Arduino pin named ```RST```. This is the Arduino reset pin. Now the button that
previously called the function ```makedark()``` will cause the program to
reset. You can verify this by noticing that it restarts your LED pattern. This pin will be very useful in restarting the pinball table.

**_CHECKPOINT!_**

That is the end of today's session. Have fun!