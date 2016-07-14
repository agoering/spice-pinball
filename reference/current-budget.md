---
layout: reference
title: Current Management
prev_section: reference-main
next_section: speaker-amp
permalink: /reference/current-budget/
---

## Choosing resistors for LEDs

LEDs have a forward voltage which can be thought of as the voltage that must be across the LED for the LED to light up (https://learn.adafruit.com/all-about-leds/forward-voltage-and-kvl). They also have a maximum current that can be pulled through without burning the LED up. These values are different for each color:

**Regular LEDs:**

- Forward voltage (red, yellow): 1.8V
- Forward voltage (green, blue): 3.3V
- Max current is 25-30mA

**RGB LEDs:**

- Forward Voltage (RGB): (2.0, 3.2, 3.2)V
- Max current is 20mA through each
- Green dominates, probably due to visual perception

If we call our forward voltage Vf, the applied voltage Vin, and our max current Imax, the equation that describes the minimum safe resistor value to keep us from burning up the LED is given by (Vin - Vf)/Imax. 

This resistance value ends up being fairly small, around 200-300 ohms. However, we usually stick with drawing 6mA current or less in each LED, for reasons of current budgeting in the shift register (which needs to stay under about 50-70 mA - 50 divided by 8 LEDs is about 6). A 6mA current puts us around 283 ohm (for green and blue) or 510 ohm (for red and yellow). When we use 470 ohm resistors, we have measured currents in the neighborhood of 6.5mA on the green, yellow, and red LEDs. This is still fine for the shift register, and puts us at a max of around 7mA * 8 = 56 mA.

**The following resistance values have been found to be both safe and tolerable to the eye:**

_On shift register:_

- Blue: 5.1k (green, brown, red)
- Red/Yellow/Green: 1k (brown, black, red)
- 1k: Regular LED, bearably bright
- 470: Regular LED, pretty dang bright (except blue - super dang bright) Green underwhelming. 

_On RGB:_

- Blue: 3.3k (orange, orange, red)
- Green and Red: 1k (brown, black, red)

Using lower resistor values is fine for the pinball machine (provided the current budget allows for it), but it can be too bright for activities. Using a 1k or 10k resistor is more appropriate (they will result in currents of around 3.2 mA or 0.32 mA, respectively). For our activities, we use 10k resistors for all LEDs.

## Protoboard Supply Current Limits

The protoboards with basic pinball setup should run at around 250 mA. The supply can provide more (up to 700mA, if the wall wart is rated up to 1A), but they can’t supply infinite current! Also, there is a limit of 40mA max through Arduino Nano pins.

**Current budget calculation:** 

Arduino + scoreboard (max) + 2*(shift register, typical) + 2*(RGB, max)  + (speaker, typ) = (40 + 30 + 2*70 + 2*9 + 10) mA = ~238 mA.

Based on the above calculation, it would be possible to run two RGB LEDs with the I/O pins (or one RGB and three life LEDs), use all of the analog input pins for sensing, and add up to 9 more shift registers to control even more LEDs. If you use large enough resistors on the shift register LEDs, then you can drive LEDs in parallel from a single shift register output. Using 1k resistors will allow about 2 in parallel (each drawing ~3.2 mA), while using 10k resistors will allow 10-20 in parallel. This is an easy way to get more blinkenlights onto your pinball machine while using the same amount of wiring on the protoboard!

The following table shows some typical component current values which were used to calculate the current budget above. Be careful to calculate your current budget afresh if you choose new resistors for your LEDs!  

+-------------------------------+----------------+------------------------------------------------------+
| Component                     | Max current    | Typical current                                      |
+-------------------------------+----------------+------------------------------------------------------+
| Breadboard power supply       | 700 mA         |                                                      |
+-------------------------------+----------------+------------------------------------------------------+
| LM78xx (for DIY supply)       | 1 A            |                                                      |
+-------------------------------+----------------+------------------------------------------------------+
| LM317 (for DIY supply)        | 1.5 A          |                                                      |
+-------------------------------+----------------+------------------------------------------------------+
| Arduino (its own consumption) |                | 40 mA                                                |
+-------------------------------+----------------+------------------------------------------------------+
| Scoreboard                    | 80 mA          | 30 mA                                                |
+-------------------------------+----------------+------------------------------------------------------+
| LEDs                          | 20 mA          | 1.8 - 3 mA (w/ 1k resistor)                          |
+-------------------------------+----------------+------------------------------------------------------+
| NPN 3904                      | < 10mA per LED | 1.8 - 3 mA (when powering LEDs through 1k resistors) |
+-------------------------------+----------------+------------------------------------------------------+
| Shift registers (each)        | 70 mA          | 50 mA                                                |
+-------------------------------+----------------+------------------------------------------------------+
| RGB LED                       | 9 mA           |                                                      |
+-------------------------------+----------------+------------------------------------------------------+
| Speaker                       |                | 10 mA (? an estimate)                                |
+-------------------------------+----------------+------------------------------------------------------+