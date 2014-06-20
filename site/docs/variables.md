---
layout: docs
title: Variables
prev_section: modifying-blink
next_section: two-leds
permalink: /docs/variables/
---


Now, we will try another program, which will make it easier for you to change the pin number and the timing. Try uploading this one:

<a href="/sketches/02_blinkvar.txt">02_blinkvar</a>

This program does the same thing as the last one, but has some
differences. It has the following lines at the top:

```int ledpin = 12;
int ontime = 500;
```

The words ```ledpin``` and ```ontime``` are variables. You could change
their names to anything you like, but you have to change it throughout the program. The word ```int``` is telling Arduino that these variables are of type ```integer```, so their value can be any integer (whole number). The first line is setting the value of the variable ```ledpin``` to 12. This way, you can use the variable name instead of writing ```12``` throughout the program, like inside ```digitalWrite()```.

The second line is setting the value of the variable ```ontime``` to ```500```.

The reason to use variables is that it makes it easy to change. For
example, try changing the pin number again, by changing the value of
```ledpin``` at the top of the program.

This changes the pins everywhere in the program. So if you had used
```ledpin``` in a 100 different places, then you don't need to change
change the program in all 100 places just to change the pin. You can do it at the top of the program once!

Try the following as well: 

1. Try changing the delay time at the top of the program. 
2. Now create a new variable (call it whatever you want), and use it to make the LED stay ON for one full second, and stay OFF for half a second.

**_CHECKPOINT!_**