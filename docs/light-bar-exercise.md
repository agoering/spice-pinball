---
layout: docs
title: Light Bar Exercise
prev_section: scoreboard-partition
next_section: music
permalink: /docs/light-bar-exercise/
---

Let's combine what we've learned about light patterns, analog sensors, and the numeric display (scoreboard) to make an indicator of the proximity sensor reading. Open the **light-bar-exercise** sketch.

Notice that before ```setup()```, we set up the shift registers and declare some variables to hole onto the sensor value. Then, inside ```setup()``` we set the LEDs to all be off. 

Inside the loop, we are cleaning up our code in a way that will be very useful for the jukebox and pinball machine. 

This sketch has a special structure, which we will use for the remainder of our sketches. Look inside the ```loop()```. There are three functions there:

1. ```readinputs();``` reads all input sensors and buttons
2. ```dologic();``` decides which functions to use based on inputs
3. ```writeoutputs();``` controls output components (such as the shift registers)

We'll use _only_ these three main functions in the loop from now on. Any other functions that we need (to decide which light patterns to play, for example, or which songs to play) will be called within these three main functions. This will help make it easier to read and troubleshoot code.

Try the following modifications (remember to save as **light-bar-exercise-mod** in your **Mods** folder!):

1. Add a numeric indicator: use the scoreboard to display the value of the analog sensor reading. You can show the raw reading, or you can use ```map()``` to change the number to a relative value; for example, between 0 and 100.
2. Modify the program to light up all the LEDs up to and including the proximity indicator LED. (Hint: a switch case structure may be useful).
3. Add a sound indicator:
    - Add a speaker to the program and make it repeatedly beep a note.
    - Make the beeps occur faster (more frequently) to indicate how close you are to the proximity sensor.
    - Make the beep tone a higher frequency as well as you get closer to the IR sensor.

**_CHECKPOINT!_**

That is the end of today's session! 
