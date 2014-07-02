---
layout: docs
title: Many shift registers
prev_section: bitwrite
next_section: timedevents 
permalink: /docs/manyshiftregs/
---


In all the previous programs, we have declared our byte variable with
the number 1 inside square brackets at the end (```byte
serdata[1];```). This is telling the arduino that the variable
```serdata``` stores 1 byte. This is also counted from 0. So it is
actually byte number 0. It can be called by using ```serdata[0]```, as
we have done.

We only use it to store 1 byte because we only needed 1 byte for 1
shift register. On your breadboard, you will see a second shift
register connected to the blue LEDs.

PICTURE OF SECOND SHIFT REGISTER
<img src="/img/wes.png" style:"width: 650px"/>

This second shift register's clock and latch pins have been shared
with the first. But its data pin is right now going to ground (0
volts).  Try removing that connection, and instead connecting its data
pin to the first shift register's Y7' pin.

PICTURE OF SECOND SHIFT DATA CONNECT
<img src="/img/wes.png" style:"width: 650px"/>

Now, as soon as the first shift register receives a new byte, it
should shift its old byte to the new shift register, which is further
down the line. Verify this.

**_CHECKPOINT!_**


Now try uploading the following program:

<a href="/sketches/s2_sh02.txt">s2_sh02</a>

In this new program, we set ```numreg``` to 2, since we want to use
two shift registers with the object ```shregs```. We also store 2
bytes in ```byte serdata[2];```. This way, calling ```
shregs.update(serdata);``` will shift out both bytes.

The two bytes of ```serdata``` can be called individually as:

```
 serdata[0] = 0b00000000;
 serdata[1] = 0b00000000; 
```

as we do inside ```setup()```. 

Take a look at the new ```changeserdata(int ff)``` function, and see
how the LED pattern is being generated. Try changing the code so the
bits are running away from each other instead of towards each other.

Did you do this by changing the ```serdata``` entries, or changing how
the flag changes?

**_CHECKPOINT!_**


In this way, you can connect as many shift registers you want, just
using 4 pins on your Arduino. The shift registers don't have to only
control LEDs. They can control any digital component, as long as you
remember to use them with transistors.


