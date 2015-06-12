---
layout: instructors
title: H-Bridges
prev_section: program-hygiene
next_section: h-bridges
permalink: /instructors/h-bridges/
---

### How H-Bridges Work

This section isn't needed to actually use the motor control boards, but it explains what's going on inside.

**[[hbridge image]]**

The integrated circuit (a **xxxx**) contains two H-bridges. An H-bridge is a set of four transistors which allow current to be directed in either direction through the motor. In the image above, we can start the motor in one direction by turning on transistors A and D while keeping B and C turned off. We can then reverse the direction by turning on B and C while keeping A and D off. If we keep all the transistors off, the motor is in a "brake" state, since when the motor is spun it generates a voltage that attempts to drive the motor in the opposite direction of motion (slowing the motor down). Finally, if transistors A and B are off while C and D are on, the motor is in a "coast" state and the motor is free to rotate.

So, we have 4 possible states we can set the motor: brake, coast, forward, and backward.