---
layout: instructors
title: SPICE Libraries
collection: instructors
prev_section: main
next_section: program-notes
permalink: /instructors/spice-libraries/
---

## What are SPICE Libraries?

The Pinball Library is a collection of Arduino functions useful for pinball programs, that work with the specific electronic components we use in camp. The SPICE Sketchbook is a collection of Arduino sketches used in these tutorials. 

### Installing the Pinball Library

1. Quit Arduino if it is open. Download the zip file from [https://github.com/dileepvr/spice-pinball](https://github.com/dileepvr/spice-pinball)
2. Unzip contents into the Arduino Libraries folder. This should create a folder called spice-pinball in the Libraries folder. (You can also place this into the Sketchbook folder with no ill effects).
3. Rename the spice-pinball folder "Pinball" (be sure to capitalize the 'P').
4. Open the Arduino IDE, and check the popup list File->Examples for your new 'Pinball' library.

### Installing the SPICE Sketchbook

1. Download the zip file from [https://github.com/ayocom/spice-arduino](https://github.com/ayocom/spice-arduino). 
2. Unzip contents and place folders directly into the Arduino folder (not the libraries folder). 
3. Rename the spice-arduino folder "Spice" (be sure to capitalize the 'S').
4. Open Arduino. The SPICE sketches should now be accessible via **File >> Sketchbook**

### Updating the Libraries using Git on the SPICE laptops

If you use git, you can clone both the Pinball Library and SPICE Sketchbook into the Arduino folder and pull changes using ```git pull```. 

To get the freshest version on the SPICE camp laptops, copy the following using ```CTRL+c``` and paste it into a Terminal window using ```CTRL+SHIFT+v```.

```
#!/bin/bash
cd ~/Pinball
git pull
cd ~/Spice
git pull
exit
```

### If your Arduino has a counterfeit FTDI chip

**Mac OSX**: See [here](http://arduino.stackexchange.com/questions/5119/arduino-nano-no-serial-port-for-macbook-air-2013), at Mekku's answer.
