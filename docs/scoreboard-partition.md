---
layout: docs
title: Multinumber Display
prev_section: scoreboard
next_section: light-bar-exercise
permalink: /docs/scoreboard-partition/
---

Let's do something a little more interesting with our scoreboard. We'll use the same button pins as in the previous session to act as inputs (4,5,6, and 7). 

Open the **scoreboard-partition** sketch fom **File > Sketchbook > Jukebox Challenge**.

We're using the same flags as before to keep track of button presses (```flag 0```, ```flag1```, ```flag2```, and ```flag3```). We define all the buttons as switches in the same manner as before.

We use the same timed event to avoid using delay. This time, we add a flag ```num2``` to keep track of a second number.

There is something new in ```setup()```: we are setting a decimal to partition the scoreboard into two areas. 

```myboard.setpartition(1);
myboard.blankpredisplay();
myboard.blankpostdisplay(); 
```

The first line tells the board where to put the decimal, which can be at location 1, 2, or 3. The second line sets the display before the decimal to be blank, and the third line sets the display after the decimal to be blank.

In the loop, we again use our very clean program structure. The ```changenum()``` function is used within the ```scoreboard()``` timed event definition, and the timed event is called inside ```writeoutputs()```. 

Read through the ```readinputs()```, ```dologic()```, and ```writeoutputs()``` functions, and see if you can predict what this program will do. Why do we need the if statement checking if ```num < 1000```?

**_CHECKPOINT!_**

Now upload the program and give it a whirl!

Try the following modifications (make sure to save as **scoreboard-partition-mod** in your Mod folder first!):

1. Change the partition location to position 2. 
2. Modify the logic for the right partition, now that it will be a 2 digit number.
3. Replace the input controlling the number in the left partition with an analog input of your choice, and use the ```map()``` function to convert the analog input to a 2-digit output. Look back to the <a href="{{ site.baseurl }}/docs/analog-ranges/">analog ranges</a> activity if you need a refresher. You don't necessarily need to use the switch case structure, but you can if you want to.


