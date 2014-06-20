---
layout: docs
title: The Trouble with Delay
prev_section: buttons
next_section: serial-monitor
permalink: /docs/delay-trouble/
---

The problem with using ```delay()``` in your pinball machine is that the
microcontroller will go to sleep, and will miss everything that
happens in the pinball machine until it wakes up again. This is bad,
because a well-programmed Robot needs to stay awake and alert at
all times.

The way we fix the problem is to stop using ```delay()```, and instead use a stopwatch. Try uploading this program:

<a href="05_nodelay.txt">05_nodelay</a>

Now, you should be able to control the LED on pin 12 using the button, as well as cause the LED on pin 11 to blink without any conflicts.

How did we do that? Well, lets take a look at the program.

The first thing to notice is that the function ```delay()``` is not being
used anywhere in the program. Instead, we are using a stopwatch.

At the top (before ```setup()```), there is a new line:

```Pb_stopwatch mywatch;
```

This is creating a stopwatch called ```mywatch``` (you can name it
something else if you like). Inside ```setup()```, there is this line:

```mywatch.start();
```

This tells the stopwatch named ```mywatch``` to start counting from zero. Later in the program, you can use the words:

```mywatch.time()
```

which will ask the stopwatch ```mywatch``` to tell you how long it has been (in milliseconds) since the last time it was 'started'.

Inside ```loop()```, the lines:

```if ( mywatch.time() > ontimeb ) {
  ledbstate = !ledbstate;
  digitalWrite(ledb, ledbstate);
  mywatch.start();
}
```

check to see if sufficient time has passed since the last time the
stopwatch (```mywatch```) was started. If the condition is met, then the LED's state (whether it's High (1) or Low (0)) is changed from what it was, to the opposite state. This line:

```ledbstate = !ledbstate;
```

changes ```ledbstate``` to 0 (if it was 1), or to 1 (if it was 0).  Note that you have to start the stopwatch inside the if-structure again, so we can keep track of the last time the LED was changed.

