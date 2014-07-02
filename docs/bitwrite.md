---
layout: docs
title: bitWrite()
prev_section: washiftregsdo
next_section: manyshiftregs 
permalink: /docs/bitwrite/
---

This is how shift registers can be used to control multiple LEDs on
you pinball machine. However, many times, you will want to change only
one or two specific LEDs, and leave all the other LEDs alone. For
this, we can use a new function called ```bitWrite()```.

Upload the following program:
<a href="/sketches/s2_sh01b.txt">s2_sh01b</a>

You should see only LED number 5 (start counting from 0) blinking.
Inside ```changeserdata(int ff)```, we are using ```bitWrite()```:

```
 if (ff == 0) { bitWrite(serdata[0], 5, 1); }
 else if (ff == 1) { bitWrite(serdata[0], 5, 0); }
```

The second argument tells ```bitWrite``` which bit (starting from 0)
to write to, and the third argument, which can only be 0 or 1, tells
it what to write it as. This leaves all the other bits untouched.

- Try changing the ```0b00000000``` assignment inside ```setup()```
  again, and verify that the other bits are untouched.
- Try blinking some LED other than LED number 5. Try LED number 0.

**_CHECKPOINT!_**

You can use the ```flag``` to do more than just switch between two patterns. Try uploading:

<a href="/sketches/s2_sh01c.txt">s2_sh01c</a>


What are the red LEDs doing? Look into ```changeflag()``` and
```changeserdata()``` and see how ```bitWrite()``` is being used.

**_CHECKPOINT!_**


