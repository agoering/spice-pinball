---
layout: docs
title: Looped soundtracks
prev_section: music
next_section: jukebox
permalink: /docs/loopedsoundtracks/
---

Now we will learn how to play a constant, looped soundtrack in the
background, just like looped timed events.

Copy the following code into your work area:

<a href="/sketches/01_blink.txt">s2_sh05b</a>

You cannot upload it yet, because in the beginning of the code, we have inserted the line:

```
#include "mysongs.h"
```

But the file ```mysongs.h``` does not exist yet. To create it, click
on the downward arrow to the upper-right corner of the arduino window
as shown:

PICTURE OF ARDUINO WINDOW WITH NEW TAB
<img src="/img/wes.png" style:"width: 650px"/>


This will open a popup menu. In it, click on ```New Tab```. This will
ask you to name the new tab. Name it ```mysongs.h```. Now your arduino
window is opening two files at the same time. You can switch between
them by clicking on the correct tab at the top bar of the window.

Copy the following code into the ```mysong.h``` file:

<a href="/sketches/mysongs.h">mysongs</a>


Now, you can upload the code.

Opening multiple tabs is a way of keeping the code more readable. We
are now defining all the songs in the new file, not in the main
program file. But we are including the new file inside the main
program file.

Do you recognise the melody?

**_CHECKPOINT!_**

Inside ```setup()```, we are calling:

```
  spkr.loopstart(marionotes2, mariotimes2, 61);
```


The arrays ```marionotes2[]``` and ```mariotimes2[]``` have been
defined inside ```mysongs.h```. The command starts playing that melody
in loop in the background. It is interrupted when ever a button is
pressed, which plays it's own melody (also defined in ```mysongs.h```).

You can stop the loop track anytime by using ```loopstop()```, just
like for looped timed events.

Note the ```spkr.update()``` line inside ```writeoutputs()```.

This program also has a new flag ```flag3```, and a new switch
```mysw3```.  Take a look at ```writeoutputs()``` function and try to
figure out what they are doing.

**_CHECKPOINT!_**

