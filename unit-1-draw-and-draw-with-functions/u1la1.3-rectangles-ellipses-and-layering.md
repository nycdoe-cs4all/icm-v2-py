---
description: How can we use shape functions to create images?
---

# U1LA1.3: Rectangles, Ellipses, and Layering

### Teacher Notes and Overview

In this learning activity, students will create a visual composition using Processing.py shape functions `rect()` and `ellipse()`. They will continue to build on their understanding of functions and their parameters to recreate the robot from lesson 1.

This lesson is split into three parts: drawing rectangles, drawing ellipses, and coding the robot.

In U1LA1.1, we practiced abstraction with the unplugged robot activity, today they will get the opportunity to code their robot.

The do-now will give students an opportunity to create a new robot (or multiple robots) and make revisions to their existing robot.

Have extra copies of the worksheet because students may make mistakes (or may have lost their sheet prior to this class). Additionally, having a paper copy of the Processing.py coordinate plane is really useful at this point in time!

**NB**: _There are two activities to practice rectangles and ellipses. Offer multiple opportunities for students to display and explain their work to the class or peers._

_Some students may want to add color, but that lesson won’t be introduced until later. The student focus should be on drawing using functions from the Processing.py library. Trust the process that styling will come later, and embrace any students who figure it out early!_

_This lesson provides opportunities for pair programming. Please note that paired programming opportunities should always have an equal number of “at-bats” for each student._

### Objectives

**Students will be able to:**

* Consult the Processing.py reference
* Create rectangles using the `rect()` function
* Create ellipses using the `ellipse()` function
* Understand the concept of layering to create images using multiple shape functions

### Suggested Duration

1-2 periods, (\~45-90 minutes)

(This may require some extension depending on how elaborate students were with their robots, but they will come back to this project later!)

### NYS Standards

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **Function -** Functions are lines of code that perform specific tasks.
* **Parameters -** Are the values inside of a parenthesis following the name of the function.
* **rect() function -** Draws a rectangle to the screen.
* **ellipse() function -** Draws an ellipse (oval) to the screen.

**Pre-Req Vocab:**

* **Width -** Horizontal distance of a 2D shape
* **Height -** Vertical distance of a 2D shape
* **Rectangle -** a 2D figure with four straight sides and four right angles
* **Ellipse -** a regular oval shape

### Planning Notes and Materials

|                                                                Planning Notes                                                                |                                      Materials                                     |
| :------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------: |
| <p>Anticipate that students may have lost their robot or want to redo their robot.<br><br>Make sure students can navigate multiple tabs!</p> | <p>Pens/Pencils<br>Highlighters<br>Rulers<br>Robot Worksheet (Extras, Printed)</p> |

### Resources

* Basics of Drawing (NEED TO MAKE PYTHON VERSION)
* [Layering Example](https://trinket.io/python/16972efcd9)
* [Robot Worksheet](https://drive.google.com/file/d/1ZmERZDHhM4A7TB27mQcxrcPJeAi5Z0m8/view?usp=sharing)
* Intro to Editor && Hello Ellipse (NEED TO MAKE PYTHON VERSION)
* Intro to Rectangle (NEED TO MAKE PYTHON VERSION)

### Assessments

**Formative:**

Ellipse and Rect position challenges

**Summative:**

Code Your Robot

Taijitu Symbol (Upcoming Mini Project)

Abstract Album Art (End of Unit Project)

### Do Now/Warm Up (\~3-5 min)

This will be an unplugged activity, it is important to review how to find the positions and sizes of the shapes used to create the robot they drew and deconstructed in lesson U1LA1.1 Ask students to take out their robot worksheet and add or make changes to it.

To review how rectangles and ellipses work in p5 ask students ask the following:

* Which corner is used to determine the position of a rectangle?
* What two values are used to determine the position of a rectangle?
* Is the width and the height of the ellipse a diameter or a radius?

### Draw a Rectangle (\~10 min)

Bring students back together to briefly code-along the `rect()` function. They should first be introduced to it along with its parameters and with examples showing different values for width and height.

Begin by introducing the rectangle function and how it works. You may have students copy it into their notes or add it onto a function poster around the classroom.\
\
**As you code discuss the following:**

* How many parameters does `rect()` accept? Use the [reference](https://py.processing.org/reference/rect.html) to show its arguments.
* How can we tell what are the “x” and “y” values of the position of a rectangle or other shapes?
* Students can copy & paste this line of code onto future sketches. This line of code displays the “x” and “y” value of the mouse location while on the canvas.

```
from processing import *

def setup():
    size(400,400)

def draw():
    background(220)
    #Code to display mouse coordinates:
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    #Code along rectangle:
    rect(200, 50, 70, 10)
    
    


draw = draw
run()
```

After discussing the `rect()`function and adding one together, ask students to experiment with changing the different argument values to alter the parameters. Then give students a moment to practice adding more rectangles, either with criteria you have given, or anywhere they'd like.

### Drawing Order

Some questions may come up about layering or drawing order if so tell them that in Processing.py, shape and color functions are rendered to the canvas in the order they're written in the program - from top to bottom.\
\
**Algorithms** - Drawing order and control flow in Processing.py is an important CS practice. This concept will appear often throughout the course.

<figure><img src="../.gitbook/assets/Screen Shot 2022-09-16 at 2.22.11 PM.png" alt=""><figcaption><p>Shows setup and draw function, setup labeled as running once, draw labeled as running in a loop.</p></figcaption></figure>

### Student Practice #1 (\~5 min)

Ask students to complete the challenge of recreating the following shapes on their canvas. **NB**: _The real challenge is recognizing how to get all their edges to show!_

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p>Grey canvas with a white square of equal size in each corner.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Grey canvas with white square in each corner and four in the center forming a larger square.</p></figcaption></figure>

[Solution Code (Trinket)](https://trinket.io/python/b80dc7987f)

This activity will reinforce students’ knowledge of coordinate points and positioning on the canvas. Some calculations will be needed in order to get the rectangles in the corner. Have some present their work and explain their solutions to the rest of the class.

Some students may want to create more squares or experiment with sizing. Circulate the room to ensure students are using comments to label the different rectangles.

**Ask students:**

What is the relationship between the x & y coordinates and the height & width?

Explain your process for layering the rectangles in the challenge.

### Draw an Ellipse (5 min)

Bring students back together to briefly code-along the `ellipse()` function. They should first be introduced to it along with its parameters and with examples showing different values for width and height. Follow the same step as with `rect()`, allowing students to adjust values before continuing. They should end up with a function like this anywhere on their page:

```
ellipse(50, 200, 100, 10) #NOTE: Processing.py requires all 4 arguments, unlike p5.js
```

**As you code, discuss the following:**

Why is the x and y in the center? There is not vertex for the ellipse to use as a starting point for the width and height. It is also made that way in case we want to draw an oval instead of a perfect circle.

Are the width and height radius or diameter? The width and height of an ellipse will serve as diameters. So that means if the height is 50 px then the radius is 25 px from the (x, y) to the top and 25 px to the bottom. Same with the width, it works horizontally.

### Student Practice 2 (\~5 min)

Ask students to add to their first practice by inscribing an ellipse in each rect, like so:

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption><p>Grey canvas with a white square in each corner and a white circle inscribed in each.</p></figcaption></figure>

This activity will reinforce students’ knowledge of coordinate points and positioning on the canvas. Some calculations will be needed in order to get the ellipse in the corner. \\

* Ask students to modify their code from before and add ellipsis to the center of their rectangles.
* Circulate the room to ensure students are using comments to label the different shapes.
* Students should duplicate their previous sketch so that they don’t have to code one from scratch and keep a copy of their original sketch.
* Have some present their work and explain their solutions to the rest of the class.

[Possible Solution](https://trinket.io/python/b80dc7987f)

### Draw Your Robot (\~10 minutes)

**NB**_: This can also be a take home project_

Draw in Processing.py the robot that you made on graph paper. Start by opening the [Blank Sketch with Mouse Coordinates](https://trinket.io/python/db10a38077) and click 'Remix' to make a copy - remember to rename and save your file so it lives in your account forever!

Students who are still having trouble with positioning can use this [starter sketch (Trinket)](https://trinket.io/python/63f86b3413) that contains the following:

* Mouse canvas position indicator (x, y)
* Adaptable grid

Make sure students read the comments in the code as they serve as instructions!

### Wrap Up (\~3 min)

Ask 2-3 students (preferably that have volunteered, or you have checked-in with) to share their code for the robot to the class. Try to call on students whether they have the right or wrong code and prompt the class to coach students through errors - this can begin to build a culture celebrating errors as learning moments. Shares work best if you make them a consistent part of your routine.

**Ask Students:**

1. When creating the robot what is the most important information that we need to gather?
2. What is a good way to keep track of shape order and layering? Provide an example.
3. What are the step to took to overcome any confusion or difficulties?
4. Explain how the coordinate system works in relation with `rect()` and `ellipse()`

### Extension

_**Ask students to check out the p5.js online reference and add more shapes to their robot, or give it a friend/pet/background.**_
