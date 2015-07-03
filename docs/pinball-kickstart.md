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

We'll use these tunes and the pinball template code to kickstart your pinball machine! If you haven't finished those tunes yet, finish them now.

Open the **pinball-template** code and save it as something else (maybe your pinball game name or team name). Have a look at your Program Outline and start adding things to the template one at a time, and test the code after each addition. Here are some suggestions, to get you started:

1. Add the reset button and light pattern that you wrote for the startup routine to the ```setup()```. (this was in **fancy-reset-pattern** in your **Mod** folder). You could add a sound effect for startup here, too.
2. Use digital inputs to control a "point scored" sound and/or a "ball dead" sound.
3. You will notice a simple digital switch on the board that we haven't used yet. Connect this to pin A3, and use this as one of your inputs.
4. Now start adding points to the board, corresponding to your inputs.
5. Try using some analog inputs to control sounds. You may want to use these as [digital switches](http://ayocom.github.io/spice-pinball/docs/analog-as-digital/), or you may come up with a clever use of an analog input. 

These things will be solid foundation for your pinball table, but continue adding things according to your Program Outline!
