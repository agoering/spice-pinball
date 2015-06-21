---
layout: docs
title: Jukebox
prev_section: scoreboard-partition
next_section: supplies-d
permalink: /docs/jukebox/
---

Now that we know how to use the scoreboard, let's make a Jukebox! This will serve as a really helpful outline for your pinball machine program.

Open the **jukebox** sketch, which should have a second tab named ```mytunes.h``` which contains the tunes.

Take a look at the overall structure of the sketch. Notice there are very long comments to help delineate different areas of the sketch. The pinball programs may become quite long, so it's helpful to do something like this to break it up and guide the eye.


Upload and verify the following: 

- Button 0 should decrease the number on the scoreboard (though it will not drop below 0).
- Button 2 should increase the number on the scoreboard.
- Button 1 should start playing the melody associated with that number.
- Button 3 stops whatever is being played.

You should also notice the shift register LEDs changing to the tune. Read through the jukebox code and get a feel for what it is doing. Then, try the following modifications (remember to save as **jukebox-mod** in your **Mod** folder first!):

- Try adding the songs you wrote earlier (they should be in your **mytunes-mod** file) to your Jukebox. Use the higher numbers for them.
- Add the reset button and light pattern that you wrote for the startup routine (this was in **reset-pattern-mod**).
- From **light-bar-exercise-mod**, you might want to use the light and tone corresponding to an analog input. This will get you one step closer to your pinball machine.
- Add additional sound effects that correspond to an analog inputs instead of to the buttons. You might want to look back to your **pinball-sounds-mod** for this.

**_CHECKPOINT!_**

Congratulations! You now have a functioning jukebox, and a head start to your pinball machine. If you still have time, go back to the other sketches in your **Mod** folder and pull out pieces of code that will be useful to your pinball machine, folding them in to your **jukebox-mod** sketch. Here are some suggestions:



- 
