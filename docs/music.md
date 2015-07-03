---
layout: docs
title: Music
prev_section: light-bar-exercise
next_section: loopedsoundtracks
permalink: /docs/music/
---

Today we're going to make some music, learn how to play sound effects on top of background soundtracks, and then build a jukebox! After that, you'll have an opportunity to use everything we've learned so far to write code that can be directly used in your pinball machine.

Connect three of the buttons on your board to pins 4, 5, and 6.

Upload the **music** sketch.

Now try pressing buttons 0, 1, and 2. What do you hear?

**_CHECKPOINT!_**

This new program is the same as the old, but has additional lines for the speaker.

At the top, we define a speaker object by supplying the speaker pin number:

```Pb_speaker spkr(13);
```

We called it ```spkr```, but you can use any other name.

The sound effects that need to be played in the speaker are declared
using pairs of arrays: one for notes, and one for timing. You can think of an array kind of like an ice cube tray: it holds a set of values that are related to one another. It's like being able to a whole set of many variables, but using only a single variable name.

In our program, we are using the array ```melody1[]``` to store the notes for the first sound effect, and the array ```timing1[]``` to store its timing.

The notes being used are your standard notes, and are actually the
sound frequencies of those notes. They can be viewed in the file **notes.h**. Here's how to find it:

Go to **Sketch >> Add File** and then add the file in **Libraries >> Pinball >> notes.h**. Now your Arduino
window is opening two files at the same time. You can switch between
them by clicking on the correct tab at the top bar of the window.

If you use a 0 for the note value, that simply corresponds to a pause in the tone sequence.

Note that we are simplyfing our loop code this time through by using functions. We have a function to read inputs, a function to calculate the logical steps needed, and a function to write to outputs. This will be a helpful way to write code for the pinball machine. For now, we have an empty logic function, but we will add to it later.

Inside the ```writeoutputs()```, we call ```spkr.update()```, which is necessary to feed information through our ```Pb_speaker``` function

We can start playing ```melody1``` on our speaker by calling ```spkr.start(melody1, timing1, 8)```. The 8 is just the length of the melody. You can play a shorter first part of the melody by using a
number smaller than 8 in the last argument. You can play the same
melody with a different timing by changing the second argument from
timing1 to some other array. You can also stop a melody by calling ```spkr.stop()```.

Try the following modifications (make sure to save as **music-mod** in your **Mod** folder first!):

1. Try adding notes to ```melody2``` by increasing the size of   ```melody2[]``` and ```timing2[]```. Remember to change the length also when its being started.
2. Try making button 1 play ```melody1``` (instead of ```melody2```), but slower. Do this by defining a new timing array called ```timing1b[]``` with longer time values, and call it when starting ```melody1```.

**_CHECKPOINT!_**
