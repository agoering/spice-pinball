---
layout: docs
title: Inside Blink
prev_section: programs
next_section: modifying-blink
permalink: /docs/blink/
---

Now, let us look at the program itself, and try to figure out what it
says. Here's that link again in case you closed the window:

<a href="{{ site.baseurl }}/sketches/01_blink.txt">01_blink</a>

The first line says: ```#include <Pinball.h>```

This line is not necessary for most Arduino programs, but we will be
using some special SPICE-camp language to program our Pinball
machines. So it is always a good idea to start your programs with this line.

The thing to note is that there are these strange words with flower
braces, and something written inside the braces. These braces are what we call functions. This program is using two functions: ```setup()``` and ```loop()```. They are used like this:

```void setup() {
     WRITE SOMETHING HERE
}
void loop() {
     WRITE SOMETHING ELSE HERE
}
```

These two functions are always necessary for the Arduino to
work. Everything written inside the ```setup()``` function is run by the
Arduino only once (at the beginning). Everything written inside the
```loop()``` function is run continuously in a "loop". For example, in the
program, the line:

```pinMode(12, OUTPUT);
```

is telling the Arduino to make pin 12 ready for putting out
voltages. This needs to be done only once, which is why it is inside
the ```setup()``` function. The rest of the lines need to run continuously
again and again, which is why they are inside the ```loop()``` function.

Let us look closely at what is inside the ```loop()``` function.

```digitalWrite(12, 1);
delay(500);
digitalWrite(12, 0);
delay(500);  
```

The line:

```digitalWrite(12, 1);
```

is telling the Arduino to write a high ("1") voltage on pin 12.
Similarly, the line:

```digitalWrite(12, 0);
```

is telling the Arduino to write a low ("0") voltage on pin 12.
The line:

```delay(500);
```

is telling the Arduino to go to sleep for 500 milliseconds, which is
half a second. 

So the Arduino is right now, setting pin 12 voltage to
high, then sleeping for half a second, then setting the pin 12 voltage to low, then sleeping again for half a second, and then repeating.

