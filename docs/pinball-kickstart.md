---
layout: docs
title: Pinball Kickstart
prev_section: template-program
next_section: 
permalink: /docs/pinball-kickstart/
---

Now that we have a template program and have practiced modifying it by adding a new system, it's time to go back to your own pinball cause and effect table. At this point, you can fill out the function column. 

During the jukebox challenge, you wrote a few new tunes and sound effects (inside **mytunes-mod.h**) to go with your pinball theme. If you haven't finished those tunes yet, you can finish them now.

Open the **pinball-template** code and save it as something else (maybe your pinball game name or team name). 

You may want to use a different combination of inputs than the pinball template. You can use the highlighted code to decide which lines to comment out (or eventually delete) if they are irrelevant to your game.

Start adding things from your cause, effect and function table to the template one at a time, and test the code after each addition. Here are some suggestions for code you have already written or learned about that can be added in (if it works with your game):

1. Add the reset button and light pattern that you wrote for the startup routine to the ```setup()```. (this was in **fancy-reset-pattern** in your **Mod** folder). 
2. Add a looped background track that plays throughout your game, with timed event sound effects that play according to different inputs. The **looped-soundtrack** code in Sounds and Senses may be helpful to look back on. Some ideas of sound effects are a "point scored" sound and/or a "ball dead" sound.
3. Add points to the scoreboard corresponding to your inputs. You can use the the scoreboard to keep track of lives, or maybe you have a different way to keep track of lives and will use the scoreboard only for score. The **scoreboard** and **scoreboard-partition** sketches may be helpful.
4. You may want to use analog inputs as <img src="{{ site.baseurl }}/docs/readsensors" style="width: 650px"/>, or you may come up with a clever use of an analog input (the one we just added, modeled after the light bar exercise, is just one example). 

Don't worry if you don't finish today. We'll have more time to do this during the rest of the week!