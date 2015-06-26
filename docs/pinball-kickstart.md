---
layout: docs
title: Pinball Template
prev_section: template-program
next_section: 
permalink: /reference/pinball-kickstart/
---

During the jukebox challenge, you did the following:

1. Wrote a few new tunes (inside **mytunes-mod.h**) that go with your pinball theme and add them to the unused higher numbers in your jukebox.
2. Make up a few sound effects that will integrate with your gameplay; for example, a "point scored" sound, or a "ball dead" sound, and maybe a "game over" sound.

We'll use these tunes and the pinball template code to kickstart your pinball machine! Here's what to do next:

1. Add the reset button and light pattern that you wrote for the startup routine to your ```setup()```. (this was in **fancy-reset-pattern** in your **Mod** folder). You could add a sound effect for startup here, too.
2. Try controlling some of the 
Now that you have some fun tunes, try controlling them with the analog inputs instead of the simple buttons. You will want to use these as [digital switches](http://ayocom.github.io/spice-pinball/docs/analog-as-digital/). You will notice a simple digital switch on the board that we haven't used yet. Connect this to pin A3, and use this as one of your inputs.

