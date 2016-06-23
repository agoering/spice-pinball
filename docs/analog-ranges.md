---
layout: docs
title: Input Ranges
prev_section: readsensors
next_section: tones
permalink: /docs/analog-ranges/
--- 

What if we want to achieve different behavior on our outputs using different ranges of analog input? We will learn how to do that now, using a new kind of logic structure called a **switch case** and a new function called ```map()```.

Open the **analog-range** sketch. 

Inside the loop, we see this:

```
int range = map(piezo_val, piezo_max, piezo_min, 0, 3);
```

This command uses the ```map()``` function to take ```piezo_val``` and break it into four pieces (called 0,1, and 2... the counting starts at 0). The largest piece starts at ```piezo_max``` and the smallest piece ends at ```piezo_min```. Each time through the loop, ```map()``` takes the value of the input, converts it to a numbered piece of the full range, and stores the result in the variable ```range```.

Just below ```map()```, we see the **switch-case** function. The function argument and first case is shown here:

```
switch (range) {
case 0:    // hard knock, turn on red LED
    Serial.print(piezo_val);
    Serial.print(" ");
    Serial.println("hard knock");
    digitalWrite(greenled_pin, 0);
    digitalWrite(redled_pin, 1);
    break;
...
}
```

The line ```switch (range)``` indicates that we want to use the variable ```range``` for each case. So, we have case 0, case 1, case 2, and case 3. 

Within each case, we print the value of ```piezo_val```, a note about what this physically corresponds to, and control our LEDs accordingly. Then, the line ```break;``` tells the Arduino to leave the **switch-case** and go back into the loop. 

Next we simply write ```speakerVal``` to ```tone()``` in the same way as before.

Instead of making modifications, brainstorm some other ways you might want to use a **switch-case** as part of a Pinball machine. Write those down.