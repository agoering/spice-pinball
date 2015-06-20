---
layout: docs
title: Light Bar Exercise
prev_section: othertimedevents
next_section: scoreboard
permalink: /docs/light-bar-exercise/
---

Let's combine what we've learned about light patterns and analog sensors to make an LED indicator of the proximity sensor reading. Open the **light-bar-exercise** sketch.

Notice that before ```setup()```, we set up the shift registers and declare some variables to hole onto the sensor value. Then, inside ```setup()``` we set the LEDs to all be off. 

Inside the loop, we are cleaning up our code in a way that will be very useful for the jukebox and pinball machine. We only call three functions in the loop. One reads all of the inputs (in this case, your analog sensor). The second performs logic operations to decide what to do based on the outputs, and the third writes to the outputs (in this case, the shift registers). We will use this structure for the pinball machine, to keep code clean and readable. 

Try the following modifications (remember to save as **light-bar-exercise-mod** in your **Mods** folder!):

1. Modify the program to light up all the LEDs up to and including the proximity indicator LED. (Hint: a switch case structure may be useful).
2. Add a sound indicator:
    - Add a speaker to the program and make it repeatedly beep a note.
    - Make the beeps occur faster (more frequently) to indicate how close you are to the proximity sensor.
    - Make the beep tone higher as well as you get closer to the IR sensor.