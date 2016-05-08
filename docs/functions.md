---
layout: docs
title: Functions
prev_section: switches
next_section: flags
permalink: /docs/functions/
---

So far, we have been using functions like ```setup()```, ```loop()```, and```digitalWrite()```. Now we will learn how to create our own functions.

Open and upload the **rgb-switches** program:

Now, all three buttons (Red, Green, and Blue) behave like switches.

In the program, before ```setup()```, you will see three switches being created:

```Pb_switch sw1(200);
Pb_switch sw2(200);
Pb_switch sw3(200);
```

These are used later inside the ```loop()``` to control the toggling.

The ```setup()``` function should be identical to the **rgb-led** program, except for the line:

```makedark();```

This is a function that is not part of the Arduino bundle. We defined
it ourselves. It is defined below the ```loop()``` function, along with other functions. You can change its name to anything you want.

When ever ```makedark()``` is called, the program basically runs through all the commands inside the ```makedark()``` function.

Inside ```loop()```, you will see that three other functions are being used (```makered()```, ```makepurple()```, and ```makegreen()```). These functions are also defined further down the program. Note that the functions make the ```loop()``` function a lot more readable. This will help you when writing particularly big programs.

Try this modification (make sure to save rgb-switches as **rgb-switches-mod** in the **Mod** folder first!):

1. You have listed all the seven color combinations as an exercise with
the previous program. We wrote the functions for red, green, blue, and purple. You should make functions to produce the other three colors. Test them out on switches 1, 2, and 3.

**_CHECKPOINT!_**

