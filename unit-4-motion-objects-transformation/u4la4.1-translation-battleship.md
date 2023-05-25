---
description: How can I move the canvas origin to effect the position of shapes?
---

# U4LA4.1: Translation Battleship

### Teacher Notes and Overview

This lesson introduces linear transformations: `translate()`, `pushStyle()`, and `popStyle()`.

Translate is a useful little skill mostly when used in conjunction with other things - on its own, it seems pretty boring and pointless. That’s okay - just acknowledge it with kids, and explain that its use is coming, but for now, they just need to learn what it does. Then they’ll get to how it can be useful.

This should be pretty direct for students as transformations are an 8th-grade math standard. This can be used to open up the idea that even in math, you aren’t really moving the shape - you’re moving the origin. This is the big takeaway from this lesson that students need to know moving forward

### Objectives

Students will be able to:

* Use `pushStyle` and `popStyle` to apply transformations to the canvas&#x20;
* Transform an entire drawing.&#x20;
* Transform some of its elements.

### Suggested Duration

45 minutes (\~1 period)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.8** Develop a program that effectively uses control structures in order to create a computer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **Transformation** - In computer graphics a common task is to transform the coordinates (position, orientation, size) of objects in the display window.&#x20;
* **Translation -** In computer graphics, translation refers to the movement of objects from one position to the other in a two-dimensional or three-dimensional plane.
* **`translate()`** - Specifies an amount to displace objects within the display window&#x20;
* **`pushStyle()`** - Saves the current drawing style settings and transformations&#x20;
* **`popStyle()`** - Restores drawing style settings and transformations

### Planning Notes and Materials

|                                                                       Planning Notes                                                                       |                                                       Materials                                                       |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------: |
| This lesson mostly consists of an exploratory game activity. Please take care to preview the lesson and make sure you are familiar without the tool works! | No extra materials needed, unless you need to turn the plugged activity into something paper-based for your students. |

### Resources

_Elements of this lesson were adapted from_ [_http://genekogan.com/code/p5js-transformations/_](http://genekogan.com/code/p5js-transformations/)

* Translation Exploration Starter Code ([Trinket](https://trinket.io/library/trinkets/ae2ac506d9))
* Translation Battleship (Plugged Starter Code) ([Level 1](https://trinket.io/python/4fdc0e46b1) | [Level 2](https://trinket.io/python/371a0dda43?showInstructions=true) | [Level 3](https://trinket.io/python/3a9183d695?showInstructions=true))
* NEED VIDEO FOR PYTHON VERSION

### Assessments

_No major assessments in this lesson - take checks for understanding as you see fit!_

### Do Now/Warm Up (\~3 min)

What would happen if you translated a point at `(10,20)` by 50 units on the x axis and 30 units on the y? Where would it end up? What if you had a point at (0,0) and translated it by 20 units on the x axis and 5 units on the y?

### About translate() (\~5 - 10 min)

**NB:** _Remind students again that translate() is a useful little skill mostly when used in conjunction with other things - on its own, it seems pretty boring and pointless right now. That's okay! Acknowledge that, remind them this will all be important later, and continue on._

An alternative to positioning elements by setting their coordinates directly is to change the position of the entire coordinate system: to move, rotate, and scale the x and y-axis.&#x20;

In Math, if we have a single point - let’s say `(0,0)` - and translate it by `(10,20)`, where would its new place be? P5 works in a similar way. We can think of it less about translating the shape and more about moving the origin, which in turn moves all shapes on the screen.&#x20;

Using the translate() function we can achieve this. This function can shift the coordinate system left, right, up, and down. Moving the coordinate system is called translation.

<figure><img src="../.gitbook/assets/image (4) (2).png" alt=""><figcaption><p>image of translate(x, y, [z]) with x and y annotated for their purpose</p></figcaption></figure>

**NB:** _The z-axis is only relevant if we are working in 3 dimensions (or layering in interesting ways), which is why it's optional!_

In these two examples, we are translating the coordinate system origin to `(40, 20)` or `(60, 70)` and then drawing a rectangle 20 pixels left and down of the origin.

<figure><img src="../.gitbook/assets/Screen Shot 2023-05-19 at 10.16.01 AM.png" alt=""><figcaption><p>Two graphs demonstrating translations that move the origin and so also the shape.</p></figcaption></figure>

As far as the rectangle is concerned, it hasn't moved at all. Its upper left corner is still at `(20, 20)`. When you use transformations, the things you draw never change position; the coordinate system itself does.

It’s important to say all of this to the students so they understand what’s happening - but also this isn’t fully going to click until they start doing it themselves. As was mentioned before, kids have a very hard time grasping why this is useful/more useful than just changing coordinates, and they aren’t really going to see full benefits until future lessons. Embrace and acknowledge that!

Because it moves the whole coordinate system, any elements drawn after the call to translate will also be affected by it. Copy and paste the [following example](https://trinket.io/library/trinkets/ae2ac506d9) in the editor and make changes to the code:

```python
from processing import *
from collide2d import *

def setup():
    size(510,350)

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    translate(mouseX, mouseY);
    ellipse(0, 0, 40, 40);
    ellipse(5, 5, 10, 10);
    ellipse(-5, -5, 5, 5);
    ellipse(55, 10, 10, 10);
    ellipse(-55, -5, 5, 5);
    
    
draw = draw
run()
```

Even though the ellipses have a static location, they all follow the mouse because the origin has been translated to wherever the mouse position is. This is useful if trying to translate a design in its entirety without doing extra math. (You can also have students adjust the values in `translate()` to test what this looks like when the shapes aren't moving.)

### Exercise #1: Draw an Ellipse at a Translated Location (\~5 min)

Modify the previous examples and do the following. Draw a white ellipse at the following translated location:

* 40 pixels to the left of the mouse cursor&#x20;
* 40 pixels to the right of the mouse cursor&#x20;
* 40 pixels over the mouse cursor&#x20;
* 40 pixels under the mouse cursor

Add two other elements that are not affected by `translate()`.

### Translation Battleship (\~15-25 min)

_For all levels, there are 'instructions' in the named tab in Trinket. It may be beneficial to also display these as slides so students can easily see them while working._

1. [**Level 1** ](https://trinket.io/python/4fdc0e46b1)**(one translation for everything)** - _Pause_ after this _to talk about adding multiple translations in a sketch, with the results being cumulative. Then, you're on to Level 2!_
2. [**Level 2**](https://trinket.io/python/371a0dda43?showInstructions=true) **(separate translations for each shape - cumulative)** - _Pause here to talk about `pushStyle()` and `popStyle()`, outlined below. These are also WILDLY USEFUL THINGS that students will not understand the use of until a bit farther into this learning activity! Once they understand the idea of pushStyle() and popStyle(), then move on to:_
3. [**Level 3**](https://trinket.io/python/3a9183d695?showInstructions=true) **(with `pushStyle()` and `popStyle()`)**

### `pushStyle()` and `popStyle()`

Sometimes, a sketch will involve multiple translations to draw the same thing in different locations. If we want to draw the same shape in multiple locations we can use push() and pop() to keep track of and revert our translations as we go.

* `pushStyle()` before a translation pushes through that translation for just the shapes listed below it.&#x20;
* `popStyle()` after a translation and shapes pops off the translation so that it does not affect anything below it.

{% code overflow="wrap" %}
```python
pushStyle() #this pushes through a trnaslation of (50,50) for the first ellipse)
translate(50, 50)
ellipse(0,0,50,50)
popStyle() #this removes the translation for future shapes

pushStyle() #this pushes through a translation of (20, 20) for the second ellipse
translate(20,20)
ellipse(0,0,50,50)
popStyle() #this removes the translation for future shapes
```
{% endcode %}

Both ellipses have all the same parameters, but appear in different places! `pushStyle()` and `popStyle()` also track and revert style and color changes -- `fill()`, `stroke()`, etc.&#x20;

Thus all translations and style/color commands made between a single `pushStyle()` and `popStyle()` apply only to the operations made between them. Take a look at the following example.

```python
#Source: genekogan.com/code/p5js-transformations/

pushStyle()
translate(50, 50)
fill(255, 0, 0)
rect(0, 0, 100, 100)
popStyle()

pushStyle()
translate(250, 150)
fill(0, 255, 0)
rect(0, 0, 100, 100)
popStyle()

pushStyle()
translate(140, 280)
fill(0, 0, 255)
rect(0, 0, 100, 100)
popStyle()
```

In this sketch, we could have achieved the same visual output by simply drawing the rectangles at those exact points. Or we could have used `translate()` without `pushStyle()` and `popStyle()` by undoing each translation manually.

For simple shapes like rectangles, it is easier to not use translations, but rather to specify the points manually. But when we begin to draw more complex shapes, or when we use other transformations, translations become advantageous.

### Wrap Up

Most of this lesson involves students playing Translation Battleship, and there are no major assessments or collectibles to turn in. At the end of class, consider debriefing how the games went with a focus on the code itself. (There is a very real world in which no one 'won' any rounds.)

* How can translate, push/pop be useful in your programs?
* What was a challenge?
* What do you still have questions about?
