---
layout: reference
title: Pinball Engineering
collection: reference
prev_section: motorcontroller
next_section: 
permalink: /docs/pinball-engineering/
---

## The Engineering Process

Engineering a pinball machine is done by following the engineering process, illustrated below:

<img src="{{site.baseurl}}/img/design-process.jpg" style="650px"/>

## Pinball Engineering:

**IMAGINE:** Brainstorm ideas for the pinball machine
**PLAN:** Draw up a proposal including a diagram and a list of supplies
**CREATE:** Make a prototype of your creation, one element at a time
**IMPROVE:** Test your prototype, one element at a time. Modify anything that doesn’t work, and move on to the next element when you are satisfied.
**PLAN, CREATE, IMPROVE** again and again!

## Prototyping Tips

Prototyping is making sure that adding a new element to your existing machine doesn’t break your code or overload your electronics. When prototyping, make sure not to overwrite your old sketch (make a new copy for every new element you add!). Here are the steps:

1. Add new element onto breadboard. Test that it works electronically as expected.
2. Write new element code
3. Test new code and make sure it doesn’t make existing elements stop working.
4. Repeat steps 1-3 until you have a fully functioning electronic prototype.

## Installation Tips

After a working prototype exists, go step by step:

1. Make a key with labels. 
2. Cut wires
3. Solder elements
4. Tape elements
5. Install elements
6. Parallelize common wires (Vcc and GND lines especially)
7. Rewire (onto breadboard, after the breadboard is mounted on the table)
8. Test
9. Tune necessary parameters (analog input thresholds, etc)
10. Play pinball and show off your skills!
