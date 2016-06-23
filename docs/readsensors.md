---
layout: docs
title: Reading Sensors
prev_section: serial-monitor
next_section: analog-ranges
permalink: /docs/readsensors/
---

Now let's get down to the business of reading sensors! 

Before ```setup()```, we name the pin to read the piezo:

```
int piezo_pin = A0
```

Also, we initialize a variable to store the number read out from the analog input pin:

```
int piezo_val = 0; //value read from piezo sensor
```

We also initialize a variable to set a detection **threshold**:

```
int piezo_thresh = 0;
```

If the output of the piezo exceeds this threshold, the LED will light up. In order to do that, we also have to set a pin to control the LED (```int ledpin = 2```) and have to set that pin as an output (```pinMode(ledpin, OUTPUT)```) inside ```setup()```. We don't need to set pin modes for analog inputs, because they can only ever be used as inputs.

Inside ```setup()```, we also start the Serial Monitor. 

Inside ```loop()``` we read the sensor value. This is done using the ```analogRead()``` function:

```
piezo_val = analogRead(piezo_pin);
```

Finally, we print those values to the Serial Monitor:

```
Serial.println(piezo_val); // ln places each reading on a new line
```

Now let's use that threshold. Try setting the threshold ```piezo_thresh``` to something other than 0 - maybe try 10, 50, or 100. For each threshold, try the following:

1. Tap directly on the piezo sensor, and see how changing the threshold affects the output.
2. Knock nearby the piezo sensor. What thresholds are low enough to pick up nearby knocks?
3. Knock somewhere farther away from the piezo sensor. What thresholds are low enough to pick up distant knocks?

**_CHECKPOINT!_**

By using a threshold, you can calibrate the sensor to be useful for different applications. For instance, you might want to install a piezo sensor on your table to detect events in which the ball rolls over the sensor (which would be hard to accomplish with a switch). In that case the magnitude of the signal wouldn't be important - you only care whether the ball rolled over directly or not. In that case, you might set a high threshold to avoid false signals. 

However, if you instead wanted to mount the piezo so that it reads in how hard the ball knocks against a part of the pinball table (the backboard, for instance), you might set the threshold low enough so that any time the ball hits the backboard hard enough, the threshold is overcome, but high enough to avoid vibrations from the pinball flippers that might give spurious results.