---
layout: docs
title: Analog Inputs
prev_section: supplies-b
next_section: proximity-sensor
permalink: /docs/analoginputs/
---

So far we have dealt only with digital inputs, which have two values: off and on, or 0 and 1. There's another class of inputs - **analog** inputs have a smooth range between two values - "off" and "full blast."  A simple kind of analog control you are familiar with is a volume knob on a radio. A dimmer switch on household lights is another example.

The Arduino has special pins for analog inputs that convert voltages between 0V and 5V to numbers between 0 and 1024. There are 8 analog pins in total, A0 through A7, that run down the left side of your Arduino. Before we explore how to read values from analog sensors, let's take a close look at three different types of sensors.
