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

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Three overlapping circles with '1' between red and green, '2' between red and blue, '3' between blue and green, and 4 between all colors.</p></figcaption></figure>

### Working with Colors in Processing.py (\~7 - 10 minutes)

After students have had a chance to make their guesses, show them this gif:

<figure><img src="../.gitbook/assets/additive mixing.gif" alt=""><figcaption><p>Red, green, and blue circles overlapping with colors between each.</p></figcaption></figure>

They will likely be surprised by the colors that get mixed, especially as the center color is _white_ and not black/brown/some nasty shade of grey. This is all very understandable, and this is the perfect opportunity to explain that when students use traditional media (paint, markers, colored pencils, etc) they are using something called _subtractive mixing._ This process actually absorbs colors from the light spectrum, so you are seeing the color that _isn't_ there.

**NB:** _Because of the way the editor is configured, the Processing.py colors will always look a little muddier - this example is from p5.js, but the general concept is the same._

Computers, in contrast, use something called _additive_ mixing. They turn on different lights - red, green, and blue - and the mix of those lights produces the color you are looking at. You can get all the same colors whether you mix subtractively or additively, it's just a different process of doing things. Because of this, it may seem weird at first to deal with the numbers that make colors on the computer.

By default, our program is set to RGB - red green blue - color mode. That means our fill, stroke, background, and any other functions that can accept/control color will take in a value for red, green, and blue to make the color. (When only one number is given, that number is used for red, green, and blue.)
