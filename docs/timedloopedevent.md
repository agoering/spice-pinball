---
layout: docs
title: Timed looped event
prev_section: timedevents
next_section: othertimedevents
permalink: /docs/timedloopedevent/
---

You can also use other triggers to stop some sequence that is already
in progress, just by calling ```dothis.stop()``` if that condition is
met. 

It is also possible to have a continuous sequence running in the
background, when nothing else is happening.

Try uploading: <a href="{{ site.baseurl }}/sketches/s2_sh03b.txt">s2_sh03b</a>

Now, the LED should be doing its regular blink from Session A. But if
you press the button, it should stop the background loop, do the
preset timed sequence, and then resume the background loop.

**_CHECKPOINT!_**

If you look at the program, we have a new sequence of integer values
and timings for the background event declared before ```setup()```:


```int val2[] = {1, 0};
int tim2[] = {1000, 1000};
```

This is the blink pattern. Inside ```setup()```, we are starting the
background loop by calling ```dothis.loopstart(val2, tim2, 2);```. The
2 at the end is just the length of the background loop.

- Try changing the ```tim2[]``` values to make the background loop go faster.
- Try increasing the size of ```val2[]``` and ```tim2[]``` to make the background loop more complicated.

**_CHECKPOINT!_**

Note the ```dothis.update()``` still needs to be called inside
```loop()``` at least once. 

The looped event can be stopped at anytime by calling
```loopstop()```. It can be restarted by using ```loopstart()```, as
we have done inside ```setup()```.

Triggering a timed sequence on the same ```Pb_timedevent``` object
will pause the loop to let the new sequence complete, then resume the
loop. This can be useful if your pinball game needs to have one kind of LED
blink pattern always going on, and change briefly to another kind when
something special happens.


