---
layout: docs
title: Music
prev_section: scoreboardwithmux
next_section: loopedsoundtracks
permalink: /docs/music/
---

Now we will learn to play sound effects on the speaker.

The score board also has a speaker pin. Connect it to the A0 pin on
the arduino.

PICTURE OF SCOREBOARD SPEAKER PIN
<img src="/img/wes.png" style:"width: 650px"/>

### A little known secret:

The pins A0, A1, A2, A3, A4, and A5 can actually be used as digital
pins 14, 15, 16, 17, 18, and 19. For example, we will use A0 as
digital pin 14.

Upload the following:
<a href="{{ site.baseurl }}/sketches/s2_sh05.txt">s2_sh05</a>


Now try pressing buttons 0, 1, and 2. What do you hear?

**_CHECKPOINT!_**

This new program is the same as the old, but has additional lines for the speaker.

At the top, we define a speaker object by supplying the speaker pin number:

```
Pb_speaker spkr(14);
```

We called it ```spkr```, but you can use any other name.

The sound effects that need to be played in the speaker are declared
using pairs of arrays, one for notes, and one for timing, just like in
timed sequences. In our program, we are using the array
```melody1[]``` to store the notes for the first sound effect, and the
array ```timing1[]``` to store its timing.

The notes being used are your standard notes, and are actually the
sound frequencies of those notes. They can be view in the file:

<a href="{{ site.baseurl }}/sketches/notes.h">notes</a>


If you use a 0, that simple corresponds to a pause in the tone sequence.



Inside ```writeoutputs()```, we call ```spkr.update()```, which is
very necessary, just like for timed events.

We can start playing ```melody1``` on our speaker by calling
```spkr.start(melody1, timing1, 8)```. The 8 is just the length of the
melody. You can play a shorter first part of the melody by using a
number smaller than 8 in the last argument. You can play the same
melody with a different timing by changing the second argument from
timing1 to some other array. You can also stop a melody by calling
```spkr.stop()```.


- Try adding notes to melody2 by increasing the size of
  ```melody2[]``` and ```timing2[]```. Remember to change the length also when its being started.
- Try making button 1 play melody1 (instead of melody2), but slower. Do this by defining a new timing array called ```timing1b[]``` with longer time values, and call it when starting melody1.

**_CHECKPOINT!_**
