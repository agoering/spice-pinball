---
layout: docs
title: Comments
next_section: switches
permalink: /docs/comments/
---

Take a look at the program. Notice that there are plenty of grey lines that have been commented out by using the ```//``` symbol. The ```//``` symbol makes everything in that line that comes after it into a comment, so it won't get uploaded into the microcontroller.

In this program, the comments have been made to help you make sense of the program. You can add your own comments as well.

Every line before the ```setup()``` function should look familiar to you, except the one that says:

```
Pb_switch bluesw(200);
```

We will get to that later.

Everything inside the ```setup()``` function should also be familiar. Use the comments as a guide to figure out what's going on inside ```setup()```.

Inside the ```loop()``` function, there are two 'if-else' structures for the Red and Green colors, that look exactly like the one in 04_button1.ino (the older program that used a single button).

Do you see exactly how the Red and Green 'if-else' structures are working?

