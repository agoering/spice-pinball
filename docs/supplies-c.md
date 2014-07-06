---
layout: docs
title: Session C
prev_section: theramin
next_section: shiftregisters
permalink: /docs/supplies-c/
---

Today we will learn to use two special chips that will be helpful in realizing our pinball machines. Also, today's setup can be used directly as a model for how to read many inputs and write to many outputs - and it can be used with a few modifications as a direct model for the pinball electronics that you will build.

- Power supply breadboards with the Session C setup:

    - Two 74HC595 shift registers (Black 16 pin chips)
    - One 74LV4051 multiplexer    (Black 16 pin chip)
    - Nine tactile push buttons
    - Eight Red LEDs
    - Eight Blue LEDs
    - One Green LED
    - Several 1kOhm resistors
    - Many jumper wires

Additionally, every table must have received a buzzer equipped Spice score-board.

The breadboard should look like this:

PICTURE OF BB
<img src="/img/wes.png" style:"width: 650px"/>


And the score-board like this:

PICTURE OF SCORE-BOARD
<img src="/img/wes.png" style:"width: 650px"/>

For the first bit, we will focus on this part of the Breadboard:

HIGHLIGHT SHIFT REG + LEDs AREA
<img src="/img/wes.png" style:"width: 650px"/>


