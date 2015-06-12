---
layout: instructors
title: Pinball and SPICE Libraries
prev_section: main
next_section: program-notes
permalink: /instructors/spice-libraries/
---


The Pinball Library is a collection of functions useful for pinball programs. We will need to download this code into our Arduino Library. Here's how:

1. Quit Arduino if it is open. Download the zip file from [https://github.com/dileepvr/spice-pinball](https://github.com/dileepvr/spice-pinball)
2. Unzip contents into the Arduino Libraries folder. This should create a folder called spice-pinball in the Libraries folder.
3. Rename the spice-pinball folder "Pinball" (be sure to capitalize the 'P').
4. Open the Arduino IDE, and check the popup list File->Examples for your new 'Pinball' library.

The SPICE Sketchbook is a collection of Arduino sketches. **Add where to find them and how to install.** Those are also available as .txt files on this website, and can be copied and pasted into Arduino if you don't have the 'Spice' library installed. 

Here are some tips and tricks that may be good to know:

> ### Using Analog pins as Digital pins:
>
> The pins A0, A1, A2, A3, A4, and A5 can actually be used as digital
> pins 14, 15, 16, 17, 18, and 19. 