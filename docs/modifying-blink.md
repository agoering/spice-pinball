---
layout: docs
title: Modifying Blink
prev_section: blink
next_section: variables
permalink: /docs/modifying-blink/
---

Let's try some modifications of the program. Whenever you modify a program from our code, make sure to "save as" a new program first. Add "-mod" to the end of the program name (for instance, **"blink-led-mod"**) and save in a new folder called **"Mods"**. If you are careful to do this every time, then you can go back and reuse the code you write during these programming sessions, and save time while making your pinball machine!

Try to modify the **blink-led** program in the following ways:

1. Change the pin being used from 12 to 11, or 10. Remember that you'll have to move the jumper wire to the correct pin on the Arduino if you change the program!
2. Change the amount of time between blinks. Can you make it so the
LED stays on for one second (1000 milliseconds), but stays off for
half a second (500 milliseconds)?
3. Cut all the lines inside the ```loop()``` function and move it into the
```setup()``` function. What does this program do? Try pressing the reset
button on the Arduino. Can you explain what the LED is doing?
<!-- 4. Move the lines back into the ```loop()``` function, and change the pin
back to 12. Now, try and make the LED do a more complicated blink
pattern, of your choice. This is good practice for your pinball machine! -->

**_CHECKPOINT!_**

Now, reopen the original **blink-led** for the next part.

