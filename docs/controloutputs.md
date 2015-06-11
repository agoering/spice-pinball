---
layout: docs
title: Controlling Outputs
prev_section: readsensors
next_section: calibration
permalink: /docs/controloutputs/
---

Now that we know how to use analog inputs, let's use them to control some outputs! Remember the RGB LED we mixed colors on before? We only used digital inputs (on and off) to make those colors. Remember, you made a table of all the possible colors. How many were there?

Now we have the ability to use analog inputs, which can be any number between 0 and 1023 instead of just 0 and 1. We will convert these to analog outputs, which will range from 0 to 255. Imagine making a table of possible colors from those 255 options on three inputs!

Instead of trying to do that, let's just write a program to do it for us. At the same time, we'll control a small speaker to make a tone corresponding to the inputs. In this way, we will build a musical instrument called a theramin!

You will need to connect your red, green, and blue RGB LED transistor bases to Arduino pins 10, 9, and 6, like so:

<img src="{{ site.baseurl }}/img/b-rgb-led-connections.png" style="width: 650px"/>

Upload the following program: <a href="{{ site.baseurl }}/sketches/s3_rgb_theramin.txt">rgb_theramin</a> 

Go ahead and fiddle with the sensors a little bit, and see what happens. Your LED color should be changing.

**_CHECKPOINT!_**

Let's have a quick look at the program. Most of it should look very familiar, but there are new functions, ```analogRead()``` and ```analogWrite()```, that we need to use analog inputs.

Again, we'll declare some variables for the analog inputs:

```//Input IR sensors
int analogIn0 = A0;     
int analogIn1 = A1;
int analogIn2 = A2;
```

Also variables for the LED outputs:

```// Output pins to RGB LED
int redled = 10; 
int greenled = 9;
int blueled = 6;
```

And also for the speaker output:

```//Initialize speaker
int speakerPin = 8;
```

We declare and initialize variables for the sensor values as before, and also for the values we will output to the LEDs and speaker.

```int sensorValue0 = 0; //value read from "red" sensor
int sensorValue1 = 0; //value read from "green" sensor
int sensorValue2 = 0; //value read from "blue" sensor
```

```int outputValue0 = 0; //value output to red LED
int outputValue1 = 0; //value output to green LED 
int outputValue2 = 0; //value output to blue LED 
```

```int speakerValue = 0; //value output to speaker
```

In the ```setup()``` loop, we'll re-initialize the Serial Monitor in case we want to see what our sensors are doing while the theramin is working: 

```Serial.begin(9600);
```

We also set the pin mode of the LED pins and speaker pin to ```OUTPUT```. Remember that we don't have to set pin modes for analog inputs.

```// set the LED pins and speaker pin to outputs  
pinMode(redled, OUTPUT);
pinMode(greenled, OUTPUT);
pinMode(blueled, OUTPUT);
pinMode(speakerPin, OUTPUT);
```

Now we get into the guts of the ```loop()```. We'll use the same Serial Monitor code as before - remember that you can comment this out with ```//``` later if you don't want to use it. 

We'll read the analog inputs in the same way:

```sensorValue0 = analogRead(analogIn0);
sensorValue1 = analogRead(analogIn1);
sensorValue2 = analogRead(analogIn2);
```

So far, so good. In the next block of code, we are producing values to send to the RGB LED, which as we mentioned must range from 0 to 255. Since we have seen that the sensor values range from 0 to 1023, we will use the ```map()``` function to convert the values. It looks like this:

```outputValue0 = map(sensorValue0, Min0, 1023, 0, 255); 
outputValue1 = map(sensorValue1, Min1, 1023, 0, 255); 
outputValue2 = map(sensorValue2, Min2, 1023, 0, 255); 
```

That tells the ```map()``` function to produce an ```outputValue``` between 0 and 255, using the sensorValue between ```Min``` and 1023. 

Finally, we use the ```analogWrite()``` function to write the ```outputValue``` to the pins we chose for outputs (the ```redled```, ```greenled```, and ```blueled``` pins). 

> It is important to note that ```analogWrite()``` only works with pins marked with the ```~``` symbol. Those are called **pulse width modulated** pins (>> **PWM** for short), and are a way to simulate an analog signal on a digital pin.

We give ```analogWrite()``` the variable names for the pin to write to, and the value to write:

```analogWrite(redled, outputValue0);
analogWrite(greenled, outputValue1);
analogWrite(blueled, outputValue2);
```