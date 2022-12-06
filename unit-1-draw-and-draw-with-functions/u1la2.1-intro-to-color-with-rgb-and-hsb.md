---
description: How do color values work in my code?
---

# U1LA2.1: Intro to Color with RGB and HSB

### Teacher Notes and Overview

In this learning activity students add color to any of their previous designs. They learn to apply the`background()`, `fill()`, and `stroke()` functions (used in scales of gray until now), to define colors and add transparency. The RGB (Red, green, blue) color model as well as HSB (Hue, Saturation, Brightness) are introduced as options for working with color.

The first part of this lesson encourages students to think critically about color mixing and the differences between subtractive mixing (which they probably have some familiarity with) and the additive mixing done on computer screens. Students may struggle a bit with RGB values, which should make HSB a breath of fresh air. For most programs it does not matter which color mode they choose to work in, and so students should be encouraged to gravitate towards whichever feels the most natural/intuitive for them.

One note is that students may struggle with order in their drawing as color is introduced. One way to frame this for students is to act out the code with colored markers, and have students walk you through their intentions. If students say 'draw a red circle,' you must first pick up the red marker, then draw the circle using the red ink - this is why stroke/fill must come before the shape they are going to be changing.

Teachers looking for a deeper dive or to make greater connections with their students are recommended to look at the optional lessons after this one to delve deeper into ways colors and data are stored.

Anticipate that many students may struggle with the idea of opacity/transparency. Anticipated responses include ‘brightness,’ ‘shade,’ ‘tone,’ etc. These are great return points for when you introduce HSB color mode.

There are many wonderful examples of color theory at work in our world. A useful one to for this topic is Olafur Eliasson’s A Room for One Color, in which the artist uses additive mixing to make every object in the room appear a uniform grey.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p>This image is not edited in any way! This is from the phenomenology art movement for anyone with curious students</p></figcaption></figure>

### Objectives

**Students will be able to:**

* Describe the process by which computers mix colors (additive mixing)&#x20;
* Use `fill()` to change the color of shapes in RGB **** and HSB color modes.

### Suggested Duration

1-2 periods (45 minutes each)

### NYS Standards

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **`fill()` function** - Sets the color used to fill shapes.This color is either specified in terms of the RGB or HSB color depending on the current `colorMode()`
* **Subtractive Mixing** - the mixing you are used to seeing with paint - paint tints absorb different lights from around them to create the visual color you see.
* **Additive Mixing** - mixing done with light - adding lights to create the different colors you see.
* **RGB** - Red, Green, Blue color mode, the default in Processing.py. Each value is 0 - 255.
* **Opacity/Transparency** - how see-through or not a shape is. (_Make sure students understand opaque to be solid and transparent to be closer to clear._)
* **HSB Color Mode**
  * **Hue** - the shade of a color
  * **Saturation** - the intensity or vividness of a color (sometimes referred to as chroma)
  * **Brightness** - the amount of white or black present in a color

### Planning Notes/Materials

|                                                                                          Planning Notes                                                                                          |                                    Materials                                   |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------: |
| Early on, students will likely rely on color pickers to determine the colors they are using. Look through in advance and determine the ones you think your students will like best to demo with! | You may want to have markers or other colors available to 'act out' your code. |

### Resources

* RGB Partner Practice Starter Code ([Trinket](https://trinket.io/python/615538d496))
* NEED WORKING WITH COLOR VIDEO AND OPT INDEPENDENT CODE | RGB Independent Starter Code ([p5 editor](https://editor.p5js.org/cmorgantywls/sketches/hX-nR7Q6o) | [repl.it](https://replit.com/@qrtnycs4all/U1LA32-Intro-to-Color-fill-Independent-Practice#script.js))
* HSB Color Application Practice ([Trinket](https://trinket.io/python/eafc6104db))
* [HSB Color System](https://learnui.design/blog/the-hsb-color-system-practicioners-primer.html)
* [HSB Color Mode](https://youtu.be/lt1lDp2aFLQ) (Youtube Video) <-- NEED PYTHON VERSION
* [Adobe Color Picker](https://color.adobe.com/create/color-wheel) | [HTML Color Codes](https://htmlcolorcodes.com/color-picker/)

### Assessments



### Do Now/Warm Up (\~3 - 5 min)

Imagine a computer program is going to draw three, semi-transparent overlapping circles. This means where they cross, the colors will mix and create a new color. What do you think those colors will be?

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption><p>Three overlapping circles with '1' between red and green, '2' between red and blue, '3' between blue and green, and 4 between all colors.</p></figcaption></figure>

### Working with Colors in Processing.py (\~7 - 10 minutes)

After students have had a chance to make their guesses, show them this gif:

<figure><img src="../.gitbook/assets/additive mixing.gif" alt=""><figcaption><p>Red, green, and blue circles overlapping with colors between each.</p></figcaption></figure>

They will likely be surprised by the colors that get mixed, especially as the center color is _white_ and not black/brown/some nasty shade of grey. This is all very understandable, and this is the perfect opportunity to explain that when students use traditional media (paint, markers, colored pencils, etc) they are using something called _subtractive mixing._ This process actually absorbs colors from the light spectrum, so you are seeing the color that _isn't_ there.

**NB:** _Because of the way the editor is configured, the Processing.py colors will always look a little muddier - this example is from p5.js, but the general concept is the same._

Computers, in contrast, use something called _additive_ mixing. They turn on different lights - red, green, and blue - and the mix of those lights produces the color you are looking at. You can get all the same colors whether you mix subtractively or additively, it's just a different process of doing things. Because of this, it may seem weird at first to deal with the numbers that make colors on the computer.

By default, our program is set to RGB - red green blue - color mode. That means our fill, stroke, background, and any other functions that can accept/control color will take in a value for red, green, and blue to make the color. (When only one number is given, that number is used for red, green, and blue.)

<figure><img src="../.gitbook/assets/Screen Shot 2022-10-17 at 8.39.07 AM.png" alt=""><figcaption><p>A slide explaining RGB and the fill of (0, 255, 0)</p></figcaption></figure>

In the example on the slide, there is 0 red value, 255 blue, and 0 green, so this would make a primary blue shade.&#x20;

There is also an optional fourth value that controls opacity. In the default RGB mode, this is also a number from 0-255. This will change how transparent or solid a color/shape look on the screen.

If you wanted to make a yellow circle without any change to opacity or transparency, it would look like this (you may or may not choose to code along with students - use your best judgement, as it's quick, but make sure the example is available):

```
fill(255, 255, 0) #color set before you draw shape
ellipse(200, 200, 50, 50) #drawn shape gets the color above it
```

If we wanted the circle to be slightly transparent, we might write the following:

```
fill(255, 255, 0, 75) #color set before you draw shape
ellipse(200, 200, 50, 50) #drawn shape gets the color above it
```

And we could also make the stroke a color:

```
fill(255, 255, 0, 75) #color set before you draw shape
stroke(255, 0, 255) #sets the color of the line around the shape
ellipse(200, 200, 50, 50) #drawn shape gets the color above it
```

Pretty cool, right? But what if we want more specific colors? We can, of course, just guess-and-check using our limited understanding of additive mixing. But it may make more sense to use a color picker. If you search 'color picker' in Google it will pull one up without you having to visit another page, and you can move the cursor to select new colors and get the numeric outputs for R, G, B values. You can also choose to use color pickers that will make whole palettes for you, like [this cool one from Adobe](https://color.adobe.com/create/color-wheel), or [this one](https://htmlcolorcodes.com/color-picker/) from HTML Color Codes.

### RGB Colors Pair Programming (\~10 - 15 minutes)

Students will work with partners to complete the RGB Partner Practice Starter Code ([Trinket](https://trinket.io/python/615538d496)). One partner will duplicate/fork the code. They will then take turns driving/navigating each row, giving a different stroke and fill color to each ellipse. At the end of their row, they switch roles.

If time permits, allow students time to share as this is the first time they've had to get excited about colors!

### Using Color with HSB Color Mode (\~7 - 12 minutes)

Begin by asking students:

What can be confusing about RGB color values? If you type three random numbers, can you always predict what the color will look like?

Likely, they will say it's difficult to predict/choose their colors. Even the bold students who may try to tell you that they can predict the color every time will struggle if given three random numbers, unless they are exceptional additive mixers. But have no fear - that is why another color mode - HSB - exists!

HSB stands for **H**ue, **S**aturation, and **B**rightness. (It is sometimes HSV, where the V is **V**alue.)

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p>3D color wheel showing hue, saturation, and value shifts in color.</p></figcaption></figure>



* **Hue** is where the color falls on the rainbow spectrum, from 0 to 360 (EX, a yellow, a red, a purple, etc).
* **Saturation** refers to how vivid the color is, or how much of the color is present, from 0 to 100. (EX: Something that is REALLY yellow looks like a highlighter).
* **Value** (Brightness) is the amount of white or amount of black present in a color, from 0 to 100.
* The alternate opacity/transparency setting (referred to as the alpha channel) still exists as an optional fourth value, but now it is 0 to 1, meaning students will need to give it decimal values.

Explain and demonstrate to students that this method is helpful for choosing colors logically, as in the following examples:

<figure><img src="../.gitbook/assets/image (10) (1).png" alt=""><figcaption><p>Slide describing the HSB for a muted red and light, vibrant blue.</p></figcaption></figure>

When students think about hue, remember that it is 0 to 360 - that means 0 and 360 are at the same place on this color wheel. (Saturation and Brightness are both 0 to 100.) Displaying an image like this can be helpful as students work:

<figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption><p>Color wheel with numbers 0 to 360 labeled around edge.</p></figcaption></figure>

When students want to use HSB color, they need to declare that in their code, like so:

```
from processing import *

def setup():
    size(400,175)
    colorMode(HSB) #you must declare this line if you want to use HSB
    
    

def draw():
    background(360, 50, 30) #this would read as HSB values


draw = draw
run()
```

They can read more about `colorMode()` and its optional settings in the [Processing.py reference sheet.](https://py.processing.org/reference/colorMode.html)

### HSB Colors Pair Programming (\~10 - 15 minutes)

This is a _very_ similar activity to what students did for RGB, but now they are using HSB values. Ask one partner to make a copy of the HSB Color Application Practice ([Trinket](https://trinket.io/python/eafc6104db)) starter code, which should look familiar. Note it now has a line to change the color mode!

In a similar protocol to before, one partner will take the role of driver and one will navigate to complete the first line, giving each ellipse its own stroke and fill color. Challenge students to avoid using color pickers this time since they can intuit most HSB colors. (If they do need to use color pickers, make sure they are using the HSB or HSV values.)

Once one role is complete, ask students to swap to complete the second row.

### Wrap Up (\~5 - 7 minutes)



Pick any assortment of the assessment questions above and put them in a Google Form where you can collect student answers and code links. A best practice is to also get links of student partners!

* What does RGB stand for?
* How does mixing on a computer differ from mixing with paints?
* A student wants only the second color in their project to be red, but with this code, everything is red! Why? (Show sample code that would make this situation true)
* A student successfully changes the color of their shapes, but their stroke is still black. What would they need to do to fix it? (Show code that matches this situation, with no `stroke()` call to change the color of the stroke.)
* What do you enjoy about working with color so far? What is frustrating about RGB colors?
* Describe hue, saturation, and brightness and what each one controls.
* What is your best guess as to what (HSB COLOR) would look like?
* Describe how you would make a muted magenta in HSB.
* How do you change to HSB in your p5 projects?

### Extensions

Ask students to open up their robot and give it some color!

