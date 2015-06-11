---
layout: docs
title: Reading Sensors
prev_section: analoginputs
next_section: analog-as-digital
permalink: /docs/readsensors/
---

Now let's get down to the business of reading these sensors!

First, make sure the red and black wires from the proximity (infrared) sensor goes to +5V and ground. Connect the green wire to pin A0 on the Arduino. 

Next, make sure the red and black wires from the piezo are connected to opposite sides of the resistor with brown, black, and green stripes, and that this is in turn connected on the black wire side to ground and on the other side to A1. 

Finally, make sure the force sensitive resistor is connected in the voltage divider configuration shown on the previous page, and that the connection between the FSR and the brown, black, and orange striped resistor is connected to A2. 

Have an instructor check your wiring. 

**_CHECKPOINT!!_**

Plug your Arduino into the computer, and plug in the breadboard. Open the Arduino program:

<img src="{{ site.baseurl }}/img/arduino-icon.png" style="width: 200px"/>

Upload the **analog-input** program.

Open the Serial Monitor. Notice that three numbers are being written out, one for each of the analog inputs. Let's have a look at the program. 

Before ```setup()```, we initialize variables to store the number read out from the analog input pins:

```int sensorValue0 = 0; //value read from proximity sensor
int sensorValue1 = 0; //value read from piezo sensor
int sensorValue2 = 0; //value read from force sensitive resistor
```

Inside ```setup()```, we start the Serial Monitor. Remember that in ```setup()``` we usually also declare input and output pins, but we don't need to set pin modes for analog inputs.

Inside ```loop()``` we read the sensor values. This is done using the ```analogRead()``` function:

```sensorValue0 = analogRead(analogIn0);
sensorValue1 = analogRead(analogIn1);
sensorValue2 = analogRead(analogIn2);
```

Finally, we print those values to the Serial Monitor:

```Serial.print(sensorValue0);
Serial.print(" "); // leaves a blank space
Serial.print(sensorValue1);
Serial.print(" "); // leaves a blank space
Serial.println(sensorValue2); // makes a new line
```

Note the lines that leave blank spaces between the numbers. Without those lines, the numbers would be squished up next to one another!

On to the fun part! Try interacting with the sensors while watching the Serial Monitor. In particular, you might want to:

1. Move your hand close to or far from the proximity sensor. 
2. What happens if you point the proximity sensor at the wall? 
3. What happens if you point the proximity sensor at the ceiling? 
4. Can you hold your hand too close to the sensor? Too far away? Try waving your hand back and forth close to and far away from the sensor. Does it sense your hand at all distances from the sensor?
5. Can you access all the way from 0 to 1023 for each sensor? Do any have a smaller actual range? 

**_CHECKPOINT!_**

