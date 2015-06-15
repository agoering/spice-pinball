---
layout: docs
title: Pinball Soundtrack
prev_section: loopedsoundtracks
next_section: supplies-c
permalink: /docs/pinball-sounds-exercise/
---

Let's put together everything we've learned today. To recap, we can now:

- Read in analog sensors
- Use analog sensors as if they were digital
- Produce an analog response (a tone) corresponding to an analog input
- Make simple tunes
- Play short sound effects over a background tune, controlled by buttons

Let's extend this in a way that you can directly use in your Pinball machine.

Save the **looped-soundtracks** sketch as **pinball-sounds-mod** and save **mytunes.h** as **mytunes-mod.h** in your **Mod** folder. Then try the following:


1. Within **mytunes-mod**, write a tune that goes with your pinball theme, to use as your background music. You can use the existing tunes as examples. 
2. Make up a few sound effects that will integrate with your gameplay; for example, a "point scored" sound, or a "ball dead" sound, and maybe a "game over" sound. Get creative!
3. Substitute your new background tune and sound effects to play on the existing button presses, in **pinball-sounds-mod**.
4. Now that you have some fun tunes, try controlling them with the analog inputs instead of the simple buttons. You will notice a switch on the board that we haven't used yet today. This is a simple digital switch. We have it hooked up to pin A3, but it can easily be on a digital input pin as well. Try changing one of the button inputs to read off of pin A3 to prove it to yourself.
5. Now you have five total switches and three analog inputs. Try making some of your sound effects correspond to inputs from your different analog inputs. At the end, you should wind up with a sketch that will be very, very useful in your pinball table. Ideally, you will use a combination of analog sensors and digital switches. You can use your analog sensors as digital, if you wish, or you might try making different outputs correspond to different ranges of signal from the analog inputs.

This is the end of today's session. Keep playing with your sketch as long as you like! Have fun!


<!-- <img src="{{ site.baseurl }}/img/arduino-newtab.png" style="width: 500px"/> -->


<!-- This will open a popup menu. In it, click on ```New Tab```. This will
ask you to name the new tab. Name it ```mysongs.h```. Now your Arduino
window is opening two files at the same time. You can switch between
them by clicking on the correct tab at the top bar of the window. -->