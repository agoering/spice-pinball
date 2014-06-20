## Formatting
shortname: formatting

- This is written in Markdown. Don't worry; it's simple.
- Title each section (each distinct page) with two hash marks as shown.
- Include a shortname metadata; this will become a filename of individual section.
- If you want subheadings, use more hash marks.

### Making a list
shortname: list

- Leave a blank line before a list
    - They can be nested
    - Like So.
    - Leave a blank line before the next section.
    
## Emphasis and images
shortname: emphasis-img

You can write **keywords** like that to make boldface. If you want italics, use _this_

Format Checkpoints like this, they are both boldface and italic

**_CHECKPOINT!_**

Say other really important things with lots of emphasis:

**_Current flows from higher voltage to lower voltage._**

Separate paragraphs by newlines.

Include png images with html, keep width at 650px or less:

<img src="/img/image1.png" style:"width: 650px"/>

Most sections will end with another checkpoint.

**_CHECKPOINT!_**

## Dealing with code
shortname: code

To link to code you want them to copy/paste, keep on using html. Put the code in a /sketches folder.

<a href="/sketches/01_blink.txt">01_blink</a>

Surround inline code snippets with fences like this:  ```setup()``` and ```loop()```. Bigger blocks go like this:

```
void setup() {

     WRITE SOMETHING HERE

}

void loop() {

     WRITE SOMETHING ELSE HERE

}
```

If you want to give suggestions for modifications, numbered lists are easy:


1. Change the pin being used from 12 to 11, or 10. Remember that you'll have to move the pin on the Arduino if you change the program!

2. Change the amount of time between blinks. Can you make it so the
LED stays on for one second (1000 milliseconds), but stays off for
half a second (500 milliseconds)?

3. Cut all the lines inside the ```loop()``` function and move it into the
```setup()``` function. What does this program do? Try pressing the reset
button on the Arduino. Can you explain what the LED is doing?

4. Move the lines back into the ```loop()``` function, and change the pin
back to 12. Now, try and make the LED do a more complicated blink
pattern, of your choice. This will be good practice for your pinball machine, so write down what you did!

4. It doesn't matter if you repeat numbers. It will render properly, I promise. 

5. So this list will go 1-6. 

That is all you should need to know. Have fun!