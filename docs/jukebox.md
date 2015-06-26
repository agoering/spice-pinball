---
layout: docs
title: Jukebox
prev_section: looped-soundtracks
next_section: supplies-d
permalink: /docs/jukebox/
---

Let's put together everything we've learned so far. To recap, we can now:

- Read in analog sensors
- Use analog sensors as if they were digital
- Produce an analog response (a tone) corresponding to an analog input
- Make simple tunes
- Play short sound effects over a background tune, controlled by buttons

Let's extend this by making a jukebox. The resulting sketch will be a very helpful template with which to build your pinball machine.

Open the **jukebox** sketch, which should have a second tab named ```mytunes.h``` which contains the tunes.

Take a look at the overall structure of the sketch. Notice there are very long comments to help delineate different areas of the sketch. The pinball programs may become quite long, so it's helpful to do something like this to break it up and guide the eye.

Upload and verify the following: 

- Button 0 should decrease the number on the scoreboard (though it will not drop below 0).
- Button 2 should increase the number on the scoreboard.
- Button 1 should start playing the melody associated with that number.
- Button 3 stops whatever is being played.

You should also notice the shift register LEDs changing to the tune. Read through the jukebox code and get a feel for what it is doing. 

**_CHECKPOINT!_**

Try the following modifications (remember to save as **jukebox-mod.ino** and **mytunes-mod.h** in your **Mod** folder first!):

1. Try writing a few new tunes (inside **mytunes-mod.h**) that go with your pinball theme and add them to the unused higher numbers in your jukebox. You can use the existing songs as templates.
2. Make up a few sound effects that will integrate with your gameplay; for example, a "point scored" sound, or a "ball dead" sound, and maybe a "game over" sound. Get creative!
3. Add the reset button and light pattern that you wrote for the startup routine to your ```setup()```. (this was in **fancy-reset-pattern** in your **Mod** folder). You could add a sound effect for startup here, too.

Congratulations! You now have a functioning jukebox, and a head start to your pinball machine. This is the end of today's session, but you might want to try the following bonus exercise.

### Bonus Exercise

Save your sketch as Now that you have some fun tunes, try controlling them with the analog inputs instead of the simple buttons. You will want to use these as [digital switches](http://ayocom.github.io/spice-pinball/docs/analog-as-digital/). You will notice a simple digital switch on the board that we haven't used yet. Connect this to pin A3, and use this as one of your inputs.

