---
layout: docs
title: Jukebox
prev_section: scoreboard-partition
next_section: supplies-d
permalink: /docs/jukebox/
---

Now that we know how to use the scoreboard, let's make a Jukebox! This will serve as a really helpful outline for your pinball machine program.

Open the **jukebox** sketch, then add a tab with ```mysongs.h```.

Take a look at the overall structure of the sketch. Notice there are very long comments to help delineate different areas of the sketch. The pinball programs may become quite long, so it's helpful to do something like this to break it up and guide the eye.

<a href="{{ site.baseurl }}/sketches/s2_sh05c.txt">s2_sh05c</a>

Now open a new tab in that window, name it ```mysongs.h```, and paste this into it:

<a href="{{ site.baseurl }}/sketches/mysongs.txt">mysongs</a>

Upload.

Verify the following: 

- Buttons 0 and 2 should cycle through the numbers on the score board.
- Button 1 should start playing the melody associated with that number.
- Button 3 stops whatever is being played.

If you have time, here are some suggestions:

- Try adding more songs to your Jukebox. Use the higher numbers for them.
- Make a menu that shows the song name beside the song number.

**_CHECKPOINT!_**

Congratulations! You now have a functioning jukebox, and a head start to your pinball machine.
