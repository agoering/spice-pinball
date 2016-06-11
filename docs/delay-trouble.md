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

The way we fix the problem is to stop using ```delay()```, and instead use a stopwatch. Upload the **stopwatch** program.

Now, you should be able to control the LED on pin 12 using the button, as well as cause the LED on pin 11 to blink without any conflicts.

How did we do that? Well, lets take a look at the program.

The first thing to notice is that the function ```delay()``` is not being
used anywhere in the program. Instead, we are using a stopwatch.

At the top (before ```setup()```), there is a new line:

```
Pb_stopwatch mywatch;
```

This is creating a stopwatch called ```mywatch``` (you can name it
something else if you like). Inside ```setup()```, there is this line:

```
mywatch.start();
```

This tells the stopwatch named ```mywatch``` to start counting from zero. Later in the program, you will see:

```
mywatch.time()
```

which asks the stopwatch ```mywatch``` to tell you how long it has been (in milliseconds) since the last time it started counting.

Inside ```loop()```, there is a new structure you haven't seen before. There's a new kind of variable called ```ledbstate```. This new kind of variable is called a **state variable**. Unlike the variables we've used before, which are set at the beginning of the program and stay the same value while the program runs, a state variable can change throughout the program. State variables are usually either 0 or 1, which in the case of an LED can correspond to off and on. 

This line:

```
ledbstate = !ledbstate;
```

changes ```ledbstate``` to 0 (if it was 1), or to 1 (if it was 0).

The if structure looks like this:

```if ( mywatch.time() > ontimeb ) {
  ledbstate = !ledbstate;
  digitalWrite(ledb, ledbstate);
  mywatch.start();
}
```

The first line, ```if ( mywatch.time() > ontimeb )```, checks to see if sufficient time (an amount given by the variable ```ontimeb```) has passed since the last time the stopwatch (```mywatch```) was started. If the condition is met, then the line ```ledbstate =!ledbstate``` changes the LED's state to the opposite. Note that you have to start the stopwatch inside the if-structure again, so that ```mywatch``` will have the correct time to report the next time around the loop. 
