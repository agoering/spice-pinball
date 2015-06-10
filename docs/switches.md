---
layout: docs
title: Switches
prev_section: rgb-led
next_section: functions
permalink: /docs/switches/
---

You will have noticed that the Blue color control works differently
from the Red and Green ones. Specifically, the Blue color stays on, or stays off, whenever the button is pressed. That is because the button is acting like a switch (think of a light switch that stays on or off).

To make the Blue button do that, we not only have to check if the
button pin is reading a Low voltage, but also that the voltage CHANGED from High to Low. We do that using a switch object. 

Before ```setup()```, you will see the line:

```Pb_switch bluesw(200);
```


The phrase ```Pb_switch``` is one of our special SPICE functions, and it is creating a switch object named ```bluesw``` (ignore the 200 for now). Further down, inside the ```loop()``` function, you will see the lines:


```blueval = digitalRead(button3);
if ( bluesw.pushed( blueval ) ) {  
  bluestate = !bluestate;
  digitalWrite(blueled, bluestate);
}
```

The variable ```blueval``` is simply there to store the voltage being read on pin 7 (```button3```). Inside the ```if``` structure brackets, the ```CONDITION```:

```bluesw.pushed( blueval )
```

checks to see of the value of ```blueval``` changed from High (1) to Low (0). You can use lines from the Serial program to check this yourself on the Serial Monitor.

When the ```CONDITION``` is satisfied, the program then 'toggles' the
blue color on the RGB LED.

Try this:

1. Make a list of all seven possible colors (even combination colors)
that you can make the RGB LED glow in using those three switches. Keep track of which buttons you had to press to make each color.

It is possible to make other colors on the RGB LED as well. We will
learn about that later.

**_CHECKPOINT!_**

