---
layout: docs
title: Force Sensitive Resistor
prev_section: piezo-sensor
next_section: readsensors
permalink: /docs/force-sensitive-resistor/
---


The final kind of analog input we'll use is a force sensitive resistor (FSR). This is a resistor whose resistance changes depending on how much pressure is applied to it. It looks like this: 

<img src="https://learn.adafruit.com/system/assets/assets/000/000/426/medium260/force___flex_FSR402_MED.jpg?1396762932" style="width: 550px"/>

There is nothing special going on with the materials here. The FSR is just a device made from two layers of metal separated by a spacer. The harder you press, the more the layers of metal touch one another through the spacer. 

FSRs are not polarized, so it doesn't matter which leg goes toward high and which goes toward ground. However, to make the resistance readable, we need to use the FSR in a circuit with another resistor, and measure the voltage in the middle. That setup looks like this: 

<img src="{{ site.baseurl }}/img/fsr-connection.jpg" style="width: 650px"/>

The FSR is useful if you want to know exactly how much it is being pressed. It can also be used to detect rollover events by your pinball, but a fun way to use it is to measure how hard a pinball smashes into it, and control outputs (or score) accordingly. 