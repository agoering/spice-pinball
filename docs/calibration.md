---
layout: docs
title: Calibrating Sensors
prev_section: controloutputs
next_section: maketones
permalink: /docs/calibration/
---

You may have noticed that some of the colors in the LED show up better than the others. We need to calibrate our theramin to fix this.

Look one more time at the ```map()``` functions. What are ```Min0```, ```Min1```, and ```Min2```? Recall that the sensors don't go all the way to zero. Because of this, if some of them have a different full range than the others, they will unfairly bias the output values. So if we use 

```map(sensorValue0, 0, 1023, 0, 255);
```

we may run into problems. Let's try an experiment to show this. 

1. Set ```Min0```, ```Min1```, and ```Min2``` to 0.
2. Upload the program, and see what color the LED is. What color do you expect it should be if you aren't in proximity to the sensors? What about if you cover the proximity sensors closely?
3. Now open the Serial Monitor and set ```Min0```, ```Min1```, and ```Min2``` to the values shown for the red, green, and blue control sensors (when your hands are away from the sensors). 
4. Upload again. Now what color is your LED when you are not near the sensors? What color is it when you move your hands in front of the A0 sensor? The A1 sensor? The A2 sensor? Does this match your expectations now?

What we have just shown is that the analog sensors have to be calibrated to make up for irregularities in their environments. Try moving the sensors around. This will uncalibrate the set. Now let's recalibrate, for practice:

1. Open the Serial Monitor.
2. Set ```Min0```, ```Min1```, and ```Min2``` to the values shown for the red, green, and blue control sensors (when your hands are away from the sensors). 
3. Re-upload the sketch.

If you wanted to avoid recalibrating often when you build your pinball machines, what do you think you should do with the sensors?

**_CHECKPOINT!_**