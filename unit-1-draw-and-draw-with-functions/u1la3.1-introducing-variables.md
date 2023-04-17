---
description: How can I use variables to store data and control values in a program?
---

# ✨ U1LA3.1: Introducing Variables

### Teacher Notes and Overview

**NB:** _This lesson technically covers NYS Standard **7-8.CT.7**_ _Design or remix a program that uses a variable to maintain the current value of a key piece of information. However, we know not all schools can guarantee a middle school sequence prior to this course. This lesson can be significantly abbreviated or skipped entirely based on the knowledge your students come in with!_

In this activity, students will be introduced to the idea of variables as a word that holds data. To begin, they will focus only on system variables built into the Processing.py library. In the next lesson, they will be introduced to creating their own variables and using the random function.

The do-now introduces a headache to make students care about the built-in width and height. Expect students to struggle; very few will have completely accurate results, but some of them may \~feel\~ that they have succeeded by having something that is centered-ish. Accept that since you’re going to rain on their parade anyway.

### Objectives

**Students will be able to:**

* Use `width` and `height` variables
* Use `mouseX` and `mouseY` to move a shape
* Use system variables as arguments for functions

### Suggested Duration

\~1 period, 45 minutes

### NYS Standards

**7-8.CT.7** Design or remix a program that uses a variable to maintain the current value of a key piece of information.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **Variables -** in CS, variables hold an assigned value or data of a specific type, they can also hold arrays of values which will be introduced later.
* **`width` -** system variable that holds width of canvas as declared in set up
* **`height` -** system variable that holds height of canvas as declared in setup
* **`mouseX` -** system variable that holds the current x-position of the mouse
* **`mouseY` -** system variable that holds the current y-position of the mouse
* **`console.log()` -** a function that logs a value to the console when the program is run.

**Pre-Req Vocab:**

* **Width -** Horizontal distance of a 2D shape
* **Height -** Vertical distance of a 2D shape

### Planning Notes and Materials

|                                                          Planning Notes                                                         |                                                                          Materials                                                                          |
| :-----------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------: |
| If your students have significant prior programming experience, please skip/adjust portions of this lesson to meet their needs. | <table data-header-hidden><thead><tr><th></th></tr></thead><tbody><tr><td><em>No extra materials required beyond a computer.</em></td></tr></tbody></table> |

### Resources

* Need video on variables in python
* Need variables on mouseX, mouseY, random() in python
* Do Now Starter Code ([Trinket](https://trinket.io/python/0c6b0dff7a))
* Blank Starter Code ([Trinket](https://trinket.io/python/db10a38077))

### Assessments

**Formative:**



**Summative:**

### Do Now/Warm Up (\~3 - 5 min)

Share students on this [sample starter code](https://trinket.io/python/0c6b0dff7a).

Instruct students to play with their code and then try to create an ellipse that is perfectly centered in their canvas. If students complete this task early, ask them to make the ellipse large enough so that the ellipse touches each edge of the canvas (if their canvas is square - if it comes out as a rectangle, touching the top and bottom will suffice).

_While students struggle, teachers will circulate and identify one or two students who have completed the task to share their work. Plug their computer into the smartboard (or otherwise display their code) - hit play again and the canvas values should reroll, creating a new canvas in which the circle is not necessarily centered._

**Ask students:** Why was this process frustrating? Why are you mad that we hit play again?

Students should realize it was frustrating guessing the center and that hitting play again changed their design, thus ruining all of their hard work.

### Center Elements with Built-In Variables Width and Height (10 min)

Students should have deduced in the Do Now that although the background values were changing, their process stayed the same - take the width and height and divide by two. To make life easier, we can abstract out the value of the width and height into a _variable._

Explain to students the definition of a variable, then explain that `width` and `height` are variables that are built directly into the p5 library and already setup to hold the size of the canvas as determined in the `size` function. We can test these variables by printing them to the console, which is a useful tool and debugging strategy that we will use throughout the year:

```python
print(width) #will display the width of the canvas
print(width/2) #will display the width divided by 2
```

Although the values are printing to the console, nothing on the screen has changed. This makes sense - we haven't used them in anything that is visibly showing up on the canvas! Instead of writing `width/2` in our `print()` function, we can use it directly in our ellipse function:

```python
ellipse(width/2, height/2, 50, 50) #this will always be centered!
```

Remind students that even though it's a word, `width` or `width/2` holds and represents a numeric value and can be used wherever we would use a number.

Once students are comfortable, set them several pair-programming tasks in a new Trinket for them to practice before moving on to the next section. For example, you might have them:

Make an ellipse that is…

* ⅓ of the way across the screen
* ¼ of the way across the screen
* ⅔ of the way across the screen
* ¾ of the way across the screen

Teachers should circulate and make notes of struggling students for conferencing or remediation. Students should be adding comments to their code to differentiate each shape they are making and where it -should- be appearing.

### mouseX, mouseY (10 min)

Students should come back together to discuss what other system variables exist (answer - many). Show students the line of code below and ask them to explain why it was useful:

```python
from processing import *

def setup():
    size(400,400)

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20) #specifically, this line!
    

draw = draw
run()
```

Explain to students that we can also use `mouseX` and `mouseY` in our functions as parameters to change our shape based on the position of the mouse, or make shapes follow the mouse. With students, code along an ellipse that follows the mouse.

Then, ask students to make a rectangle with their partner that follows the mouse. After 1-2 minutes, ask students to come back together and explain what is different between the ellipse and the rectangle. Students should recognize that the ellipse “attaches” to the mouse at its center, while the rectangle follows the upper left corner.

Use this as a launch to explain `rectMode()` and how it can be used to help position rectangles if students want them centered. Sometimes if students are doing calculations based around a point, `rectMode` on the center might make things a bit more difficult.

Once students are comfortable with using mouseX and mouseY with the position of the shape then have them…

* Use `mouseX` and/or `mouseY` to change the height or width of a rectangle
* Use `mouseX` and/or `mouseY` to change the height or width of an ellipse
* Use `mouseX` and/or `mouseY` to change the background color of the canvas
* Use `mouseX` and `mouseY` to change the fill of a rectangle or ellipse

### mouseX and mouseY for many points (10 min)

Getting a simple shape to follow the mouse is great, but what if we want to use a more complicated shape, like a triangle or a quad that is defined by many points? While we can still use `mouseX` and `mouseY`, but we need to do it a little differently. Gather students for a brief code-along using any triangle:

```python
triangle(50, 50, 75, 10, 100, 50)
```

Now if we want this triangle to follow our mouse, we will need to pick one point to 'anchor' and we will need to remember it's original coordinates. This will be the point that follows the mouse. We can do this with the first point like so:

```python
triangle(mouseX, mouseY, 75, 10, 100, 50) #point was at 50, 50
```

If we just run this code, you'll notice the triangle stays put but one coordinate will stretch and follow the mouse around. This is cool, but not what we want to have happen. We want the whole triangle to stay preserved and follow the mouse. But if we change the other points to mouseX and mouseY, we lose our triangle.

Instead, we need to do a little math to make the other points follow _at a distance_ so that our triangle preserves its shape but moves with the mouse. For example, for the second point, we can try this:

```python
triangle(mouseX, mouseY, mouseX+25, mouseY-40, 100, 50) #point was at 50, 50
```

We replaced the 75 with `mouseX + 25` because the original anchor point was at 50, and 50 and 75 are +25 units apart. We replaced the 10 with `mouseY - 40` since the original anchor point was 50, and 50 and 10 are -40 units apart. If we repeat this with our last point, we will have a triangle that follows our mouse:

```python
triangle(mouseX, mouseY, mouseX+25, mouseY-40, mouseX+50, mouseY) #point was at 50, 50
```

Notice that `mouseY` stayed the same in our final point, since it had the same value as our initial anchor point.

Time permitting, ask students to create another triangle or quad and try this process on their own!

### Wrap-Up (\~5 min)

Display several examples of student work with successes in changing colors and sizes. You will also want to choose and display several examples of students who attempted to get a triangle to move with the cursor - don’t plan on picking perfect triangles (if students did succeed, pick them last).

If your class struggled, base your discussion around problems they encountered rather than a tutorial. If they are close to finding a solution and you have extra time, you can walk them through in a code-along, but do not anticipate or force getting to that place.

**Ask Students:**

1. **How does math play a role in our Processing.py sketches ?**
2. **What are the way we can use system variables in our sketches?**
3. **How can comments help us out when using variables?**

### Extension

Ask students to duplicate their Taijitu symbol file and try to get it to follow the mouse!
