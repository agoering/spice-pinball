---
layout: docs
title: Scoreboard
prev_section: light-bar-exercise
next_section: scoreboard-partition
permalink: /docs/scoreboard/
---

Now we will learn to display numbers on the scoreboard. Our scoreboard has 4 digits and looks like this: 

<img src="{{ site.baseurl }}/img/scoreboard-front.png" style="width: 650px"/>


We will use a new class object (```Pb_scoreboard```) to talk to it.

Look at the back of the scoreboard. The pins are labeled - you should see from bottom to top GND (ground), VCC (positive voltage input), DIO (data pin), and CLK (clock pin).

<img src="{{ site.baseurl }}/img/scoreboard-back.png" style="width: 650px"/>

Connect your scoreboard as follows:

- ground (GND) to ground line on breadboard
- voltage in (VCC) to +5V line on beadboard
- data (DIO) pin to Arduino pin 9
- clock (CLK) to Arduino pin 8

**_CHECKPOINT!_**
Open the **scoreboard** sketch fom **File > Sketchbook > Jukebox Challenge**.

What are the numbers on the scoreboard doing?

Inside the program, we are declaring a ```Pb_scoreboard``` object called ```myboard```:

```Pb_scoreboard myboard(clkpin, diopin);
```

Using this object, we can display any number we want on the score
board, just by typing ```myboard.showdisplay( the number )```. 

Inside ```setup()```, we flash a ```0000```, a blank display, then a ```0```, by calling several functions sequentially. The first is the ```myboard.showdisplay(0, true)``` to get what we call "leading zeros". Then, we blank out the display using ```myboard.blankdisplay();```. Finally, we use ```myboard.showdisplay(0);``` to get a zero without "leading zeros."

Press the reset button (or reupload the program) and watch carefully to see the difference between the zero function and the leading zero function. You can choose whichever you like in your pinball machine.

**_CHECKPOINT!_**

Now, let's get to the useful bit - using our scoreboard to keep count of something!

We're using a flag called ```num``` to keep track of a number to display, and use a function called ```changenum()``` to change the flag ```num```. 

We'll use a timed event called ```Pb_timedevent scoreboard(changenum)``` to avoid using the ```delay()``` function. Note that the size of the looped event arrays ```val[]``` and ```timing[]``` is 1. A size 1 looped event is another way of doing something regularly without using a stopwatch.

Inside the loop, all we do is update our timed event. So the code that the loop executes refers to the timed event. Since that timed event calls the function ```changenum()```, that function acts as if it is being called inside the loop. This is a useful way to keep code clean. You'll learn more about this in the rest of the session.

Look at the function ```changenum()``` and see if you can figure out what it is doing. 

Try the following modifications:

- Change something inside the ```changenum()``` function so the numbers count down instead of count up.
- Change the speed at which the numbers count down.

**_CHECKPOINT!_**


