---
layout: reference
title: Speaker Amplification Circuit
prev_section: current-budget
next_section: sketch-guide
permalink: /reference/speaker-amp/
---


A <a href="http://electronics.stackexchange.com/questions/129277/how-many-volts-can-a-1-watt-8-ohm-speaker-take">“Class A” amplifier arrangement</a> works well to keep a quiet speaker output for activities and prevent large current draw: 

<img src="http://i.stack.imgur.com/vxynt.png" style="width: 50px"/>

Without the capacitor, the setup is louder. R1 can be dropped down to 470Ohm (for a 10.6 mA draw). For the final machines, the speaker can most likely be used with a direct connection to pin 13 for highest volume. We haven't verified that this draws a safe current from that Arduino pin, but we haven't broken anything either!

