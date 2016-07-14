---
layout: docs
title: Pinball Template
prev_section: jukebox
next_section: pinball-kickstart
permalink: /docs/template-program/
---

### Program Architecture

Most of our programs come down to one operation:

```if (CONDITION == TRUE){
    doVERB();
}
```

For example, if we have a button called ```cupcake``` and we want to add five points to the scoreboard when it is pressed, we could write:

```if (cupcake == LOW){
    addfivepoints();
}
```

Here, ```addfivepoints()``` is a **function** that we need to define somewhere. Everything that you want to have happen in your program - every **verb** - should have some corresponding function. This function always corresponds to that verb - turn on lights, add to scoreboard, play a tone or a tune.

We wrote a plan for what we want our pinball game to do (remember the cause and effect table?), and we can turn all of those effects (verbs!) into functions. We will start with a pinball template program, and then add one effect and function at a time, checking after each addition that the program still works as intended. It's generally a good idea to save often, especially if you have a working program and are about to make a BIG change to it. 

The pinball template sketch consists of code to control a reset button, a drain switch, a "rolling" switch, and a piezo sensor. The template sketch is written so that it can be used with the same breadboards you have been using in the tutorials. 

You will notice a simple digital switch on the board that we haven't used yet. This is the "rolling" switch. Connect this to pin A3.

Now upload the pinball template sketch from **File > Sketchbook > Pinball Template > pinball-template** and play around with it to get a feel for what it does. 

Let's now look at the pinball template sketch and compare it to its cause and effect table. Notice that each system is a single cause with multiple effects, and how each effects corresponds to some function or command. Within this program, any arrays storing information for tunes or LED patterns are stored in arrays.h. This will help keep the code clean.

The drain switch system (cause, effects, and functions) has been highlighted in pink in the template code. Your instructor will point out the location of each piece of code and why each piece of code is necessary. 

Next, you will be challenged to highlight in the code corresponding to the rolling switch and the piezo in different colors. This exercise should help you to see how many different places a single subsystem enters into the code. Your instructor will reveal the solution at each step. 

When you add new subsystems, you generally start with the cause and effect, and then write the functions that correspond to that effect. 

Let's do an exercise to see how to add a new subsystem, by adding a new system with an analog piezo. What we want to do is add 10 points to the scoreboard when the piezo is above some threshold (decided by you). Also, it should play a tone on the speaker and light up the bar of LEDs in proportion to the piezo output value. This will be very similar to the light bar exercise you did in the Sounds and Senses session, and you might find that code helpful to look back on now.

Your task is to add a new row to the cause and effect table. Write out clearly the cause and effects that this new system should have. Then, after you look back at your light bar exercise modification code, write down in the functions column the new functions that may need to be added for each effect to work.

Finally, you can start coding. It may help to make comments that explain what you want your new piece of code to do. For example, in the ```dologic()``` function, what would you need to check to determine whether to change the speaker tone or light up a different LED? After you do this, you can add your new functions and commands, and add new integers, timed events, etc as they become necessary. When you compile, if you didn't define a new integer that you call in your code, the compiler will tell you in an error message (it's very helpful that way!). 

Go ahead and try this now. Make sure to save as **pinball-template-mod** in your **Mod** folder! After a bit, your instructors will give you an example solution.





