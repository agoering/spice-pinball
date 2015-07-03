---
layout: docs
title: Looped soundtracks
prev_section: music
next_section: jukebox
permalink: /docs/loopedsoundtracks/
---

Now we will learn how to play a constant, looped soundtrack in the
background.

Connect your last button to pin 7.

Open the **looped-soundtracks** sketch. Note that it has another button, and we added all of the following to support the new button:

- ```int button3 = 7```
- ```Pb_switch sw3(100)```
- ```flag3```
- ```pinMode``` declaration in ```setup()```
- read instruction for ```flag3``` inside the ```readinputs()``` function

You cannot upload the sketch yet, because in the beginning of the code, we have inserted the line:

```#include "mytunes.h"
```

But the file ```mytunes.h``` does not exist yet. To create it, go to **Sketch >> Add File** and then add the file in **Libraries >> Pinball >> mytunes.h**. 

<!-- <img src="{{ site.baseurl }}/img/arduino-newtab.png" style="width: 500px"/> -->


<!-- This will open a popup menu. In it, click on ```New Tab```. This will
ask you to name the new tab. Name it ```mysongs.h```. Now your Arduino
window is opening two files at the same time. You can switch between
them by clicking on the correct tab at the top bar of the window. -->

<!-- Copy the following code into the ```mysong.h``` file:

<a href="{{ site.baseurl }}/sketches/mysongs.txt">mysongs</a>
 -->

Now, you can upload the code.

Opening multiple tabs is a way of keeping the code more readable. We
are now defining all the songs in the new file, not in the main
program file. But we are including the new file inside the main
program file.

Do you recognize the melody?

**_CHECKPOINT!_**

Inside ```setup()```, we have:

```spkr.loopstart(marionotes2, mariotimes2, 61);
```

This is another example of a **looped event**. The arrays ```marionotes2[]``` and ```mariotimes2[]``` have been
defined inside ```mysongs.h```. The command starts playing that melody
in loop in the background. It is interrupted whenever a button is
pressed, and each button plays a different melody (also defined in ```mysongs.h```).

You can stop the loop track anytime by using ```loopstop()```, just
like for looped timed events.

Note the ```spkr.update()``` line inside ```writeoutputs()```.

The program has a new flag ```flag3```, and new switch ```mysw3```.  Take a look at ```writeoutputs()``` function and try to
figure out what they are doing.

**_CHECKPOINT!_**

Next we'll put together everything we've learned so far!