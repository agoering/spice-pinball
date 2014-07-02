---
layout: docs
title: Reading Sensors
prev_section: analoginputs
next_section: controloutputs
permalink: /docs/readsensors/
---

The Arduino has special pins for analog inputs that convert voltages between 0V and 5V to numbers between 0 and 1024. There are 5 analog pins in total. Let's now explore how to read values from the proximity sensors. 

Make sure your breadboard is unplugged from the wall power. Plug the **GND** Arduino pin into one of the breadboard's ground buses (holes by the blue lines). Connect pins A0, A1, and A2 to the green wires from the left, middle, and right proximity sensors. It may help to label the sensors with A0, A1, and A2 on pieces of tape to help you keep track of which is which. Have an instructor check your wiring before moving on.

**_CHECKPOINT!_**

Plug your Arduino into the computer, and open the Arduino program. 

<img src="{{ site.baseurl }}/img/arduino-icon.png" style="width: 300px"/>

Open the ```analog_input``` sketch from File > Sketchbook > libraries > Session B. 

Upload the sketch and then plug in the breadboard. 

Open the Serial Monitor. Notice that three numbers are being written out. So far, we have only monitored a single input at once. This sketch improves upon this, by monitoring three inputs. Let's have a look at the program. 

Before ```setup()```, we declare variable names for our analog input pins:

```int analogIn0 = A0;     
int analogIn1 = A1;
int analogIn2 = A2;
```

We also declare variables and initialize values for the number read out from the analog input pins:

```int sensorValue0 = 0; //value read from "red" sensor
int sensorValue1 = 0; //value read from "green" sensor
int sensorValue2 = 0; //value read from "blue" sensor
```

In ```setup```, we start the Serial Monitor. Remember that in ```setup()``` we usually also declare input and output pins, but we don't need to set pin modes for analog inputs.

Now in the loop we read the sensor values. This is done using the ```analogRead()``` function:

``` sensorValue0 = analogRead(analogIn0);
  sensorValue1 = analogRead(analogIn1);
  sensorValue2 = analogRead(analogIn2);
  ```

Finally, we print those values to the Serial Monitor:

```  Serial.print(sensorValue0);
  Serial.print(" "); // leaves a blank space
  Serial.print(sensorValue1);
  Serial.print(" "); // leaves a blank space
  Serial.println(sensorValue2); // makes a new line
```

Note the lines that leave blank spaces between the numbers. Without those lines, the numbers would be squished up next to one another!

On to the fun part! Try the following: 

1. Move your hand close to or far from the proximity sensor. 
2. What happens if you point the proximity sensor at the wall? 
3. What happens if you point the proximity sensor at the ceiling? 
4. What is the true range of values of the signal? Does it go from 0 to 1024, or is the actual range smaller?
5. Can you hold your hand too close to the sensor? Too far away? Try waving your hand back and forth close to and far away from the sensor. Does it sense your hand at all distances from the sensor?

**_CHECKPOINT!_**

