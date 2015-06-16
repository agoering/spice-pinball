---
layout: docs
title: Scoreboard
prev_section: light-bar-exercise
next_section: jukebox
permalink: /docs/scoreboard/
---

Now we will learn to display numbers on the scoreboard. 

The scoreboard also uses shift registers, and has data, clock, and
latch pins. But we will use a different class object (```Pb_dislay```) to talk to it.

Look at the back of the scoreboard. The pins are labeled - you should see from bottom to top VCC (positive voltage input), GND (ground), SER (data pin), CLKS (clock pin), CLKR (we will call this the latch), and some speaker pins. We won't use the speaker pins yet.


<img src="{{ site.baseurl }}/img/scoreboard-back.jpg" style="width: 650px"/>


Connect your scoreboard as follows:

- clock (CLKS) to Arduino pin 8
- latch (CLKR) to Arduino pin 9
- data (SER) pins to Arduino pin 10
- ground (GND) to ground line on breadboard.

Now upload this: <a href="{{ site.baseurl }}/sketches/s2_sh04b.txt">s2_sh04b</a>


What are the numbers on the scoreboard doing?

**_CHECKPOINT!_**

Inside the program, we are declaring a ```Pb_dsplay``` object called ```disp```:

```Pb_display disp(datapin2, clkpin2, latchpin2);
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


