---
layout: docs
title: Analog as Digital
prev_section: analog-ranges
next_section: analog-tones
permalink: /docs/analog-as-digital/
---

Analog inputs are unique because of the fact that can detect a range of events, rather than just on or off (like a button). Those on and off only (button) inputs are called **digital inputs**. 

Sometimes, you may want to use an analog input as a digital input. For instance, you might want to install a piezo sensor to detect the ball rolling over the piezo, but not care about how forceful the impact was. 

The way to do that is by using a **threshold**. Let's look at an example. Open the **analog-as-digital** sketch from the **Sounds and Senses** sketchbook.

First, connect the resistor from the green LED-transistor-resistor setup to pin D2. 

Next, we need to find the thresholds for our sensors. We'll use the Serial Monitor to do this. Upload the program and open the Serial Monitor. What are the minimum and maximum values of each sensor? Record the minimum values in the variables ```Min0```, ```Min1```, and ```Min2```. You may want to add a small amount to those minimum values, especially if the device reads a minimum of 0. 

Now re-upload the program. Try interacting with the piezo in different ways. What causes the green LED to light up?

**_CHECKPOINT!_**

Let's have a look at the code in ```loop()```:

```if (sensorValue0 > Min0 && sensorValue1 > Min1 || sensorValue2 > Min2){
  digitalWrite(ledpin, 1);
}
else {
  digitalWrite(ledpin, 0);
}  
```

This looks like the if statement we've seen for digital buttons:


```if ( digitalRead(buttonpin) == LOW ) {
  digitalWrite(ledpin, 1);
}
else {
  digitalWrite(ledpin, 0);
}
```

However, there's more going on inside the ```if()``` condition parentheses. Instead of just reading whether a digital button is ```LOW```, we're checking the following condition:

```sensorValue0 > Min0 && sensorValue1 > Min1 || sensorValue2 > Min2
```

This is saying "If ```sensorValue0``` is greater than ```Min0``` and ```sensorValue1``` is greater than ```Min1```, or if ```sensorValue2``` is greater than ```Min2```, then do the thing in the curly braces."

So, only if you engage BOTH the IR AND the piezo, OR just the force sensitive resistor by itself, do you turn on the light. Each analog sensor is acting like a digital button, and we are using combinations to achieve different effects.

Let's try some modifications (make sure to save as **analog-as-digital-mod** first in your **Mod** folder!). You might want to save these modifications outside the loop as functions, as they may come in handy in a later session.

1. Try making the LED light only when the piezo and FSR are both pressed hard.
2. Try making the LED turn on when the piezo is pressed, then turn off when the FSR is pressed. 