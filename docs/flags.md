---
layout: docs
title: Flags
prev_section: functions
next_section: external-power
permalink: /docs/flags/
---

This will be the last program for the day.

Try uploading the the following program:

<a href="{{ site.baseurl }}/sketches/08_flags.txt">08_flags</a>

Now, pressing the button on pin 10 will cycle through a sequence of
colors. Note down the order of the sequence on a piece of paper.

Pressing the button on pin 7 will cycle through the same sequence
backwards. Verify this.

Pressing the button on pin 8 will reset the RGB LED to dark.

Note that all three buttons are working as switches.

Now let us look at the program. There is one new line before ```setup()```:

```int flag = 0;
```

The ```flag``` variable (here being set to '0') will be used to keep track of which color is currently being lit. It is a way to give the program some memory.

The ```setup()``` function is identical to the previous one (from
07_funcs.ino).

The ```loop()``` function is using two new functions:

```changenext();
changeback();
```

Do you see how they are being used? See further down the program for
what these functions are doing.

The ```changenext()``` function contains the following lines:

``` if (flag == 0) {flag = 1; makered(); }
 else if (flag == 1) {flag = 2; makegreen(); }
 else if (flag == 2) {flag = 3; makeblue(); } 
 else if (flag == 3) {flag = 4; makepurple(); }  
 else if (flag == 4) {flag = 1; makered(); }   
```

This is a new way to use the ```if-else``` structure, to check for
multiple conditions. These lines are checking what the ```flag```
variable's value is, and then setting it to the next one in sequence,
as well as changing the color.

Compare the functions ```changenext()``` and ```changeback()```. Do you see the difference? 

Try the following:

1. Change the sequence of colors to green, purple, blue, red. Make
this change in both ```changenext()``` and ```changeback()``` functions. 
2. Use the new functions that you defined for other colors in the
previous program (put them in this program as well), and make the
color sequence longer. The ```flag``` variable will need to take larger values for this.
3. There is actually a bug in the program. Can you find it?

**_CHECKPOINT!_**