---
layout: docs
title: Functions
prev_section: switches
next_section: flags
permalink: /docs/functions/
---

So far, we have been using functions like ```setup()```, ```loop()```, and```digitalWrite()```. Now we will learn how to create our own functions.

Open and upload the following program:

<a href="./sketches/07_funcs.txt">07_funcs</a>

Now, all three buttons (Red, Green, and Blue) behave like switches.

In the program, before ```setup()```, you will see three switches being created:

```Pb_switch sw1(200);
Pb_switch sw2(200);
Pb_switch sw3(200);
```

These are used later inside the ```loop()``` to control the toggling.

The ```setup()``` function should be identical to the previous program (06_RGBsws.ino), except for the line:

```  makedark();
```

This is a function that is not part of the Arduino bundle. We defined
it ourselves. It is defined below the ```loop()``` function, along with other functions. You can change its name to anything you want.

When ever ```makedark()``` is called, the program basically runs through all the commands inside the ```makedark()``` function.

Inside ```loop()```, you will see that three other functions are being used (```makered()```, ```makepurple()```, and ```makegreen()```). These functions are also defined further down the program. Note that the functions make the ```loop()``` function a lot more readable. This will help you when writing particularly big programs.

You have listed all the seven color combinations as an exercise with
the previous program. Now, try making your own functions that produce
those colors. Try calling them when ever a button is switched.  Use
the comment system (```//```) to retain mulitple lines while using only one of them.

**_CHECKPOINT!_**

