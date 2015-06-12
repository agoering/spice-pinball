---
layout: docs
title: Input Ranges
prev_section: analog-tones
next_section: music
permalink: /docs/analog-ranges/
--- 

Now, we can use analog inputs as digital inputs (acting like they are only on or off), or as fully analog inputs (where they can have a full range of signal from 0 to 1023). 

What if we want to achieve different behavior on our outputs using different ranges of analog input? We will learn how to do that now, using a new kind of logic structure, **switch case** and a new function, ```map()```.

Open and upload the **analog-range** sketch. This sketch will use the force sensitive resistor and the speaker. Open the Serial Monitor and squeeze the force sensitive resistor. What does this program do?

Let's look at a few new code elements. First, in addition to ```Min0```, ```Min1```, and ```Min2```, we added ```Max0```, ```Max1```, and ```Max2```. For now, these are all 1023, but these values may change (especially for the proximity sensors once they are mounted to your table).

Inside the loop, we see this:

```int range = map(sensorValue2, Min2, Max2, 0, 3);
```

This ```map()``` function is taking ```sensorValue2```, and breaking it into four pieces (called 0,1,2, and 3... the counting starts at 0). The smallest piece starts at ```Min2``` and the largest piece ends at ```Max2```. Each time through the loop, ```map()``` takes the value of the input, converts it to a numbered piece of the full range, and stores the result in the variable ```range```.

Just below ```map()```, we see the **switch-case** function. The first case is shown here:

```switch (range) {
 case 0:    // no squeeze
   Serial.print(range);
   Serial.println("no reading");
   speakerVal = 0;
   break;
...
}
```

The line ```switch (range)``` indicates that we want to use the variable ```range``` for each case. So, we have case 0, case 1, case 2, and case 3. 

Within each case, we print the value of range, what this physically corresponds to, and change the variable ```speakerVal``` accordingly. Then, the line ```break;``` tells the Arduino to leave the **switch-case** and go back into the loop. 

Next we simply write ```speakerVal``` to ```tone()``` in the same way as before.

Instead of making modifications, brainstorm some other ways you might want to use a **switch-case** as part of a Pinball machine. Write those down before moving on.