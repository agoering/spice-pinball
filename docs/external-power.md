---
layout: docs
title: Set Arduino Free!
prev_section: flags
next_section: supplies-b
permalink: /docs/external-power/
---


You will notice that throughout the day, we had the GND (ground) pin
of the Arduino connected to the blue-stripe rows (zero volts, or low
voltage) lines on the breadboard. This is important as it as a way for the two electronic platforms (the Arduino and the Breadboard) to agree on what constitutes a Low voltage.

You will also notice that the Arduino seems to only work when the USB
cable is plugged in, because the computer is powering it. Try
unplugging the USB cable and controlling the LEDs.

In you final Pinball table, you will not be allowed to keep your
computers hooked up to the Pinball machines. So you need to know how
to power your Arduino using the breadboard power supply.

It is very easy to do this. Just use a jumper wire to connect the pin
on the Arduino called 'Vin' to one of the red-stripe row holes on the
breadboard as shown.

<img src="{{ site.baseurl }}/img/external-power.png" style="width: 650px">

Now, the program that you previously uploaded onto the Arduino using
your computer is still inside it, and is working, even though the
computer is no longer connected to it.

WARNING: The 'Vin' pin must only be supplied with 5 Volts worth of
voltage. Any higher voltage will damage the Arduino.

That is the end of today's session. Have fun!