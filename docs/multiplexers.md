---
layout: docs
title: Multiplexers
prev_section: othertimedevents
next_section: scoreboard
permalink: /docs/multiplexers/
---


We have learnt now to use shift registers to expand the number of
digital output pins. But we have a way to expand the number of input
pins as well. We use another kind of 16 pin chips called multiplexers:

<img src="http://pinout-circuits-images.dz863.com/6/SN74LV4051A-Q1.jpg" style="width: 300px"/>


The multiplexer has three address pins (pinA, pinB and pinC), and a
common pin (COM). Setting the right address bits on A, B and C will
automatically connect the COM pin to one of the channel pins (Y0 to Y7),
which on your breadboard should be connected to 8 buttons.

<img src="{{ site.baseurl }}/img/c-buttons-mux.png" style="width: 650px"/>

To use the multiplexer, connect the A, B, and C pins to the arduino
pins 2, 3, and 4, and connect the COM pin the arduino's pin 7 as
shown (disconnect the old button if it is in the way):

PICTURE MUX CONNECTIONS
<img src="{{ site.baseurl }}/img/c-mux-connect.png" style="width: 650px"/>


Now upload:

<a href="{{ site.baseurl }}/sketches/s2_sh04.txt">s2_sh04</a>


Now try pressing any of the 8 buttons (labelled 0 to 7). What to the
shift register LEDs do?

**_CHECKPOINT!_**


The line:

```
Pb_muxin mymux(2, 3, 4, 7); // (pinA, pinB, pinC, COMpin)
```

tells the arduino that we have connected a multiplexer (mux for short)
to pins 2, 3, 4, and 7. You can then check channel number 5 by calling
```mymux.probe(5)```, and it will return its digital voltage value.

We have a new function that accepts two input arguments:

```void changeserdata(int ff, boolean val) {
bitWrite(serdata[0], ff, !val); 
bitWrite(serdata[1], ff, !val);
}
```

The first argument ```ff``` is of type ```int```. That is just any
integer number. The second argument ```val``` is the logic type
```boolean```, which means it can only be 0 or 1. It is just a bit. We
are supplying and LED number to the first, and the state of a button
(using ```probe()```) for the second, inside ```loop()```.

- Try changing things inside ```loop()``` so button 0 triggers LED 7, button 1 triggers LED 6, and so on.


**_CHECKPOINT!_**

These channels can also be used as switches, as we will see later.


