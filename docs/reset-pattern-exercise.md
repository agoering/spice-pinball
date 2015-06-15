---
layout: docs
title: Reset Pattern Exercise
prev_section: external-power
next_section: supplies-b
permalink: /docs/reset-pattern-exercise/
---

Once we set Arduino free from the computer, it will simply run the last program that was uploaded. But what if you want to restart that program to the beginning? For example, in your pinball game, you might want to restart the program after every game. We'll learn how to do that now, and make a fun pattern on the RGB LED that only happens right after the Arduino is reset.

First the easy part: disconnect the jumper cable
from pin 8, and instead connect it to the Arduino pin named ```RST```. This is the Arduino reset pin. Now the button that
previously called the function ```makedark()``` will cause the program to
reset. There is nothing you need to add in your code to accomplish this! (If you want to keep the ```makedark()``` feature, you'd just add another button, connected to ground in the same way as the ones already on your board.)

Now let's make a fun pattern on our RGB LED. Reconnect the Arduino to your computer via the USB cable. Open your **flags-mod** program, and save it as **reset-pattern-mod**. You will leave the contents of ```loop()``` alone, but will add a function with an RGB light pattern and call that function inside ```setup()```. 

Copy the ```changenext()``` function, paste it just above, and change the name to ```resetpattern()```. Modify this in any way you want to. 

When we call a function in ```setup()```, it is ok to use ```delay()```. That's because ```setup()``` isn't listen for any inputs. For instance, you could use something like this:

```resetpattern();
delay(250);
resetpattern();
delay(250);
resetpattern();
delay(250);
```

where you would want to repeat as many times as you have flags in your pattern. What this would do is run ```resetpattern()```  with flag = 0 (reset pattern will change the flag to 1), delay for 250 milliseconds, run ```resetpattern()``` with flag = 1, delay for 250 milliseconds, and so on.

However, there is an easier way: the **for loop**. Here's how the same code would look using a for loop:

```for (int i=0; i <= 3; i++){
      flag = i;
      resetpattern();
      delay(250);
  }
```

The line ```for (int i=0; i <= 3; i++)``` says "For values of i starting at zero, as long as they are less than three, run the contents of the curly braces and then add one to i." The line ```flag = i``` sets the flag to tell ```resetpattern()``` what to do. We would need to make sure, in this case, that the number of flags we have in ```resetpattern()``` is the same as the number in ```i <= 3```. 

In whatever way you choose, put your new light pattern inside ```setup()``` (you will want to do it near the end, probably just above ```makedark()```).

Upload, and watch what happens. Try pressing the reset button connected to pin 8. When you do, the pattern from the function you put inside ```setup()``` should play once, and then it should return to the normal RGB control behavior. The same thing will happen when you press the white reset button on the Arduino itself.

Now you know how to restart a program using an external input. This will be very useful in restarting the pinball table. 

**_CHECKPOINT!_**

That is the end of today's session. Have fun!