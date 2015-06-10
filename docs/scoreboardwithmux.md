---
layout: docs
title: Multiplexed Scoreboard
prev_section: scoreboard
next_section: music
permalink: /docs/scoreboardwithmux/
---


Now upload the following program:

<a href="{{ site.baseurl }}/sketches/s2_sh04c.txt">s2_sh04c</a>


Try pushing the buttons 0, 1, and 2, and see what happens to the number on the score board.

**_CHECKPOINT!_**


Inside the program, we are declaring three switch objects for the three buttons:

```Pb_switch mysw0(50), mysw1(50), mysw2(50);
```

We are also using three flags to keep track of whether or not they were pushed.
Inside ```loop()```, we are calling three standard functions:

```readinputs();       // Read all the input sensors
dologic();          // Perform logical operations
writeoutputs();     // Control all output components
```

Your final pinball code can also use this structure.

Inside ```readinputs()```, we reset flags to 0, and then store the
switch pushes from the probed buttons 0, 1, and 2 in them.

Inside ```dologic()```, we are changing the value of ```num``` based
on which flags are 1.

Inside ```writeoutputs()```, we check if any of the flags are
non-zero, and if so, then we write the new num to the score
board. Remember, there is no need to write num to the score board if
the number matches what it is already displaying. So we only write to
the score board when something changes num.


- Make it so that pressing button 1 makes the score 42 instead of 50.

**_CHECKPOINT!_**

There is a problem with the code. If more than one button is pressed,
then all modifications to num are applied in sequence of their
occurrence inside the code. How will you fix this?


