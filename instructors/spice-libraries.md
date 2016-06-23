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

To get the freshest version on the SPICE camp laptops, copy the following using ```CTRL+c``` and paste it into a Terminal window using ```CTRL+SHIFT+v```. You can also save as a shell script.

```
#!/bin/bash
cd ~/sketchbook/libraries/Pinball
git pull
cd ~/sketchbook/Spice
git pull
exit
```

## If you accidentally reset a Chromebook

### Install GalliumOS
1. Ensure developer mode is enabled (the [ ! ] screen should show up on boot, and you have to press CTRL-D to get past it). If not then turn on the device and hold ESC+REFRESH and tap POWER.
2. Start up and log in. Open a terminal with CTRL-ALT-T and type “shell” and press enter.
3. Paste the following command:
    ```cd ~; curl -L -O http://mrchromebox.tech/firmware-util.sh; sudo bash firmware-util.sh```
4. Choose option (1).
5. Choose option (N).
6.  Choose option (8) to reboot. At login, press CTRL-D
7. Press CTRL-ALT-RIGHTARROW (the right arrow by the ESC key)
8. Login as chronos
9. Type in the following command: 
    ```curl -Os https://chrx.org/go && sh go -U spicegirl```
10. After reboot, press CTRL-D. The computer will fix itself! You will need to type in the following command:
    ```Curl -Os https://chrx.org/go && sh go -U spicegirl```

### Configure Gallium

1. Log into the UO Secure wireless with PEAP authentication. Click "No CA certificate is required," and uncheck "Ask for this password every time"
2. Open Chrome. Set the home page to ```http://agoering.github.io/spice-pinball/docs/introduction/```
3. Go to Settings -> Screensaver and disable screensaver. 
4. Go to Settings -> Power Manager -> System and at the bottom, unclick "Lock screen when system is going for sleep"


### Install Arduino and Sketchbooks

Put the following in a shell script and run: 

```
#!/bin/bash
# Script to setup basic arduino and spice software.

sudo apt-get update
sudo apt-get -qq install arduino
sudo apt-get -qq install emacs
sudo apt-get -qq install git
mkdir ~/sketchbook
cd ~/sketchbook
git clone https://github.com/ayocom/spice-arduino.git
mv spice-arduino Spice
cd libraries
git clone https://github.com/dileepvr/spice-pinball.git
mv spice-pinball Pinball
arduino
```

### If your Arduino has a counterfeit FTDI chip

**Mac OSX**: See [here](http://arduino.stackexchange.com/questions/5119/arduino-nano-no-serial-port-for-macbook-air-2013), at Mekku's answer.
