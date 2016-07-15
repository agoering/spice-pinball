---
layout: reference
title: Current Management
prev_section: main
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

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg .tg-yw4l{vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-yw4l">Component</th>
    <th class="tg-yw4l">Max current</th>
    <th class="tg-yw4l">Typical current</th>
  </tr>
  <tr>
    <td class="tg-yw4l">Breadboard power supply</td>
    <td class="tg-yw4l">700 mA</td>
    <td class="tg-yw4l"></td>
  </tr>
  <tr>
    <td class="tg-yw4l">Arduino (its own consumption)</td>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l">40 mA</td>
  </tr>
  <tr>
    <td class="tg-yw4l">Scoreboard</td>
    <td class="tg-yw4l">80 mA</td>
    <td class="tg-yw4l">30 mA</td>
  </tr>
  <tr>
    <td class="tg-yw4l">LEDs with NPN 3904</td>
    <td class="tg-yw4l">20 mA</td>
    <td class="tg-yw4l">3 mA (with 1k resistors)</td>
  </tr>
  <tr>
    <td class="tg-yw4l">Shift registers (each)</td>
    <td class="tg-yw4l">70 mA</td>
    <td class="tg-yw4l">50 mA</td>
  </tr>
  <tr>
    <td class="tg-yw4l">RGB LED</td>
    <td class="tg-yw4l">9 mA</td>
    <td class="tg-yw4l"></td>
  </tr>
  <tr>
    <td class="tg-yw4l">Speaker</td>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l">10 mA (estimated)</td>
  </tr>
</table>

(References: [Arduino draw](http://arduino.stackexchange.com/questions/926/what-is-the-max-power-consumption-of-arduino-nano-3-0), [Scoreboard draw](http://www.aliexpress.com/store/product/LED-4-Digit-0-56-Tube-Display-D4056A-Module-with-Decimal-Point-for-Arduino/1213753_32505028589.html))