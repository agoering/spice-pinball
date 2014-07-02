---
layout: docs
title: Scoreboard
prev_section: multiplexers
next_section: scoreboardwithmux
permalink: /docs/scoreboard/
---

Now we will learn to display numbers on the score board.

The Scoreboard also uses shift registers, and has data, clock, and
latch pins. But we use a different class object (```Pb_dislay```) to talk to it.


PICTURE OF SCOREBOARD WITH PIN LABELS
<img src="/img/wes.png" style:"width: 650px"/>


Connect the score board's clock, latch, and data pins to arduino pins
8, 9, and 10 respectively. Also connect the score board's ground pin
to the 0 volts line on the bread board. Now upload this:

<a href="/sketches/s2_sh04b.txt">s2_sh04b</a>


What are the numbers on the score board doing?

**_CHECKPOINT!_**

Inside the program, we are declaring a ```Pb_dsplay``` object called ```disp```:

```
Pb_display disp(datapin2, clkpin2, latchpin2);
```

Using this object, we can display any number we want on the score
board, just by typing ```disp.print_number( the number )```. Inside
```setup()```, we write the number 00 by calling
```disp.print_number(0);```.

Also note that the size of the looped event arrays ```val[]``` and
```timing[]``` is 1. A size 1 looped event is another way of doing
something regularly without using a stopwatch.

- Change something inside ```changenum()``` function so the numbers count down instead of count up.
- Change the speed at which the numbers count down.

**_CHECKPOINT!_**


