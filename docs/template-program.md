---
layout: docs
title: Pinball Template
prev_section: motorcontroller
next_section: 
permalink: /reference/template-program/
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

We wrote a plan for what we want our pinball game to do (remember the cause and effect table?), and we can turn all of those effects (verbs!) into functions. Then we'll write a skeleton program that's totally empty except for the names of the functions. We'll add the body of each function and call them in the loop one at a time, checking after each addition that the program still works without breaking. It's generally a good idea to save often, especially if you have a working program and are about to make a BIG change to it. 

Let's use the instructor table as an example. Here's what its skeleton would look like:

<a href="{{ site.baseurl }}/sketches/skeleton.txt">jukebox_skeleton</a>

It contains only the names of the functions that you want to be called in the loop, and the functions are all called in the loop but commented out. Now let's say we added in a function, the ```readinputs()``` function. Now it looks like this:

<a href="{{ site.baseurl }}/sketches/skeleton_inprogress_1.txt">jukebox_skeleton</a>

Notice that we uncommented ```readinputs()``` to test it, and added the variables and setup code that we need in order to use ```readinputs()```.

Now, let's say we add the function ```dologic()```. Notice that we've commented out the ```readinputs()``` in the loop and uncommented the ```dologic()``` function, in order to isolate ```dologic()```. Also, the variables and setup code needed for ```readinputs()``` have also been added. 

We can continue this process until we finally have the jukebox sketch: <a href="{{ site.baseurl }}/sketches/instructor-table.txt">s2_sh05c</a>


