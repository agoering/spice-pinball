---
layout: instructors
title: For Instructors
collection: instructors
prev_section: 
next_section: spice-libraries
permalink: /instructors/main/
---

## So you want to host an electronics camp?

We would love for our course content to be used, reused, and remixed! 

Our activities may be helpful as written, and our Pinball library and SPICE Sketchbook are available online. The next sections will walk educators through installation of those files, and additional pages here go into more depth about the electronics and programming elements. We also have additional suggestions for ways to modify the curriculum to make it shorter (our camp is a two week course culminating with Pinball machines, but there are lots of fun day and multi-day projects buried within!). 

There are lots of other awesome resources for DIY electronics online. We recommend:

- [Arduino official site](http://www.arduino.cc/)
- [AdaFruit, a super cool resource for parts and great tutorials](http://www.adafruit.com/)
- [SparkFun, for more cool supplies](https://www.sparkfun.com/)
- [Fritzing, an open source breadboard-modeling, circuit-diagramming, and even PCB-making tool!](http://fritzing.org/home/)

Here's how to access the libraries:

The Pinball Library is a collection of functions useful for pinball programs. We will need to download this code into our Arduino Library. Here's how:

1. Quit Arduino if it is open. Download the zip file from [https://github.com/dileepvr/spice-pinball](https://github.com/dileepvr/spice-pinball)
2. Unzip contents into the Arduino Libraries folder. This should create a folder called spice-pinball in the Libraries folder.
3. Rename the spice-pinball folder "Pinball" (be sure to capitalize the 'P').
4. Open the Arduino IDE, and check the popup list File->Examples for your new 'Pinball' library.

The SPICE Sketchbook is a collection of Arduino sketches. It is also available from Github:

1. Download the zip file from [https://github.com/ayocom/spice-arduino](https://github.com/ayocom/spice-arduino). 
2. Unzip contents directly into the Arduino folder.
3. Rename the spice-arduino folder "SPICE".
3. Open Arduino. The SPICE sketches should now be accessible via **File >> Sketchbook**

If you want to share what your projects, ideas, code, or more, get in touch with us (see the footer for contact info)!
<!-- 
{% for faq in other_faqs %}
<h2><a href="{{ faq.url }}">{{ faq.title }}</a></h2>
{{ faq.content }}
<hr />
{% endfor %}
 -->
{% for article in site.instructors %}
<a href="{{ site.baseurl }}{{ article.permalink }}">{{ article.title }}</a>
<hr />
{% endfor %}