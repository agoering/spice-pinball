---
layout: docs
title: Controlling Outputs
prev_section: readsensors
next_section: maketones
permalink: /docs/controloutputs/
---

Now that we know how to use an awesome new analog input, let's use them to control some outputs! Remember the RGB LED we mixed colors from before? We only used digital inputs (on and off) to make colors before. Do you remember how many colors that was?

Now, we have the ability to use analog inputs, which go from 0 to 1024 instead of just 0 and 1. We will convert these to analog outputs, which will range from 0 to 255. Imagine making a table of possible colors from those options on three inputs!

Instead of trying to do that, let's just use a program to do it for us. At the same time, we'll control a small speaker to make a tone corresponding to the inputs. In this way, we will build a musical instrument called a theramin!

Upload the following program: <a href="{{ site.baseurl }}/sketches/s3_rgb_theramin.txt">rgb_theramin</a> 

Before you upload, let's have a look at the program:

Again, we'll declare some variables for the analog inputs, and also for the LED outputs and speaker output. 

```//Input IR sensors
int analogIn0 = A0;     
int analogIn1 = A1;
int analogIn2 = A2;

// Output pins to RGB LED
int redled = 10; 
int greenled = 5;
int blueled = 6;

//Initialize speaker
int speakerPin = 8;
```

We also declare and initialize variables for the sensor values as before, and also for the values we will output to the LEDs and speaker.

```
int sensorValue0 = 0; //value read from "red" sensor
int sensorValue1 = 0; //value read from "green" sensor
int sensorValue2 = 0; //value read from "blue" sensor

int outputValue0 = 0; //value output to red LED
int outputValue1 = 0; //value output to green LED 
int outputValue2 = 0; //value output to blue LED 

int speakerValue = 0; //value output to speaker
```

In the ```setup()``` loop, we'll re-initialize the Serial Monitor in case we want to see what our sensors are doing while the theramin is working. We also set the pin mode of the LED pins and speaker pin to ```OUTPUT```. Remember that we don't have to set pin modes for analog inputs.

```void setup(){
  //Serial register, comment out if desired
  Serial.begin(9600);
  
  // set the LED pins and speaker pin to outputs  
  pinMode(redled, OUTPUT);
  pinMode(greenled, OUTPUT);
  pinMode(blueled, OUTPUT);
  pinMode(speakerPin, OUTPUT);

  // note that analog inputs do not require pin mode settings
    
}
```

Now we get into the guts of the ```loop()```. We'll use the same Serial Monitor code as before - remember that you can comment this out with ```//``` later if you don't want to use it. 

We'll read the analog inputs in the same way:

```sensorValue0 = analogRead(analogIn0);
  sensorValue1 = analogRead(analogIn1);
  sensorValue2 = analogRead(analogIn2);
```

So far so good. In the next block of code, we are producing values to send to the RGB LED, which as we mentioned must range from 0 to 255. Since we have seen that the sensor values range from 0 to 1023, we will use the ```map()``` function to convert the values. It looks like this:

```
 outputValue0 = map(sensorValue0, Min0, 1023, 0, 255); 
  outputValue1 = map(sensorValue1, Min1, 1023, 0, 255); 
  outputValue2 = map(sensorValue2, Min2, 1023, 0, 255); 
```

That tells the ```map()``` function to produce an ```outputValue``` between 0 and 255, using the sensorValue between ```Min``` and 1023. 

Finally, we use the ```analogWrite()``` function to write the ```outputValue``` to the pins we chose for outputs (the ```redled```, ```greenled```, and ```blueled``` pins). 

It is important to note that analogWrite only works with pins marked with the ```~``` symbol. Those are called **pulse width modulated** pins (PWM for short), and are a way to simulate an analog signal on a digital pin.

We give ```analogWrite()``` variable names for the pin to write to, and the value to write:

```analogWrite(redled, outputValue0);
  analogWrite(greenled, outputValue1);
  analogWrite(blueled, outputValue2);
```

What are ```Min0```, ```Min1```, and ```Min2```? Recall that the sensors don't go all the way to zero. Because of this, if some of them have a different full range than the others, they will unfairly bias the output values. So if we use 

```map(sensorValue0, 0, 1023, 0, 255);
```

we may run into problems. Let's try an experiment to show this. 

1. Set ```Min0```, ```Min1```, and ```Min2``` to 0.
2. Upload the program, and see what color the LED is. What color do you expect it should be if you aren't in proximity to the sensors? What about if you cover the proximity sensors closely?
3. Now open the Serial Monitor and set ```Min0```, ```Min1```, and ```Min2``` to the values shown (when your hands are away from the sensors). 
4. Upload again. Now what color is your LED when you are not near the sensors? What color is it when you move your hands in front of the ```A0``` sensor? The ```A1``` sensor? The ```A2``` sensor? Does this match your expectations now?

What we have just shown is that the analog sensors have to be calibrated to make up for irregularities in their environments. Try moving the sensors around. This will uncalibrate the set. If you wanted to avoid recalibrating often when you build your pinball machines, what do you think you should do with the sensors?

**_CHECKPOINT!_**

