---
layout: docs
title: What Shift Registers Do
prev_section: shiftregisters
next_section: bitwrite 
permalink: /docs/washiftregsdo/
---

You are able to control 8 LEDs with just 4 pins!

Lets look at the code. At the top, you will see:

```
Pb_outputs shregs(datapin, clkpin, latchpin, numreg);
```

This is a way to tell the Arduino that you have connected shift
registers to it on those pins (data, clock, and latch). The fourth
argument ```numreg``` is telling the Arduino the number of shift
registers being connected, which is right now set to 1.

The shift register we use is one of those black chips in the
breadboard with 16 legs. The legs have identities:

SCHEMATIC OF SHIFT REG
<img src="/img/wes.png" style:"width: 650px"/>

Note that it has 8 output pins. It is possible to write any digital
value you want to those eight pins using the data, clock and latch
pins. The pin named Y7' can be used to connect more shift registers to
it. We will explore that in a few moments.

In the code, we have defined a new variable ```byte serdata[1];```.
This stores 1 byte, or 8 bits of digital information. Inside
```setup()```, we assign it values by typing:

```
 serdata[0] = 0b00000000;
```

This sets all 8 bits to 0. Then, we can shift these values to the
shift register (which we have named ```shregs```) by typing:

```
 shregs.update(serdata);   // Shifting out the array
```

This will set all the LEDs to not light up at the starting. 

- Try pressing the reset button and see what happens to the red LEDs
for a moment.
- Try changing some of those zeros in ```0b00000000``` to ones,
  upload, and see what reset does.

**_CHECKPOINT!_**


The rest of the program should be pretty easy to understand. We
already now how to use stopwatches, and we have defined two functions.
The function ```void changeflag()``` just changes the variable
```flag``` from 1 to 0 or 0 to 1.

The function ```void changeserdata(int ff)``` has a new variable
inside the brackets, which we haven't seen before. It simply means
that this function has to be used with an ```int``` type variable or
number supplied to it. For example, inside ```loop()```, it is being
called like this:

```
   changeserdata(flag);
```

So it is being supplied with the value of ```flag```. Inside
```changeserdata(int ff)```, it captures this value into its own
private variable called ```ff```. ```ff``` can only be used inside
this function. Right now, it is being used to change the LED pattern
conditionally depending on the value of ```flag```:

```
 if (ff == 0) { serdata[0] = 0b00111100; }
 else if (ff == 1) { serdata[0] = 0b11000011; }
```

Do you see how these ones and zeros correspond to the LEDs that are
glowing? Try changing them and see how the LEDs change.

**_CHECKPOINT!_**


