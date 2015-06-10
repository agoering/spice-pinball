---
layout: docs
title: Transistors
prev_section: breadboards
next_section: arduino
permalink: /docs/transistors/
---

In the next page, we will start using programming to control LEDs. But we need to learn about one more component before we
begin. It is called the **transistor**, and it has three legs.

<img src="https://learn.adafruit.com/system/assets/assets/000/002/340/large1024/learn_arduino_transistor.jpg?1396782029" style="width: 650px"/>

One of the legs (the middle one) is called the **base**, and is used to control the amount of current flowing through the other two legs. You have to supply a small amount of current to the base to get current to flow. Here's an illustration:

<img src="https://learn.adafruit.com/system/assets/assets/000/002/348/large1024/learn_arduino_transistor.png?1396782158" style="width: 650px"/>

To make the second red LED (connected to a resistor and a transistor) light up, use a wire to connect the base of the transistor to a high voltage as shown below. As in the LED case, we will use a resistor between the high voltage and the transistor base. 

<img src="{{ site.baseurl }}/img/led-transistor-connection.png" style="width: 650px"/>

The circuit that you just made work is drawn like so:

<img src="{{ site.baseurl }}/img/led-transistor-circuit_schem.png" style="width: 400px" align="center"/>

Notice that even though the LED is connected to a high voltage, the circuit is not complete unless the transistor base is also connected to a high voltage. This is what completes the circuit and allows current to flow to ground. 

Look closely at the way the components are plugged into the breadboard. Can you trace the way current moves through the circuit? Look back at the breadboard internal connection image if needed.

**_CHECKPOINT!_** 

We will **always** use transistors to control outputs with the Arduino. That way, the Arduino only has to provide enough current for the base, which is very small compared to the current that may be demanded by different outputs. This will help to protect the Arduino. 
