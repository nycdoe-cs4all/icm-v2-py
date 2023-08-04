---
description: How can I create a function that will draw a design?
---

# U1LA4.3: Draw with Functions

### Teacher Notes and Overview

In this lesson, students will write their first custom function that will perform an action on the screen. Today, that action will be to draw a smiley face (or other design of your choosing, if you’d like to showcase something else!).

This lesson is very teacher-heavy as students get introduced to the thought process behind writing functions. However, it is closely followed by a mini-project that will allow them to complete work independently and explore some of these ideas on their own.

### Objectives

**Students will be able to...**

* Create a function that draws a design&#x20;
* Incorporate parameters to control aspects of their function such as position

### Suggested Duration

1 Period (\~45 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.5** Modify a function or procedure in a program to perform its computation in a different way over the same inputs, while preserving the result of the overall program.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

_Review:_

* Function&#x20;
* Arguments&#x20;
* Parameters

### Planning Notes and Materials

|                                                                            Planning Notes                                                                           |                                                                              Materials                                                                              |
| :-----------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| This lesson is mostly delivered in a code along. Prior to the lesson, ensure you have a working Smartboard/Projector and students have computers available to them. | This lesson is mostly delivered in a code along. Prior to the lesson, ensure you have a working Smartboard/Projector and students have computers available to them. |

### Resources

* [Draw with Functions](https://youtu.be/iaKjQI2FPHE) (Youtube Video)
* Lesson Starter Code ([Trinket](https://trinket.io/python/57a789a162))

### Assessments

**Formative:**

* `happyFace()` function (Formative)
* `angryFace()` function (Formative)

**Summative:**

* Create an Emoji (Upcoming Mini Project)
* Abstract Album Art (Upcoming Final Project

### Do Now/Warm Up (\~5 minutes)

Display link to starter code ([Trinket](https://trinket.io/python/57a789a162)) and ask students to duplicate the code so they can be ready to begin the lesson. If you would like, this is also a great place to put an SEL check, like asking students to complete a mood meter, journal, or otherwise react to how their day or week is going.

### Code Along: Happy Face (\~15 - 20 minutes)

In this code along, you will build a function called **`happyFace()`** that will take the existing code for the happy face and turn it into a function. While the first step in the code along is always the same, subsequent steps can be a choose-your-own-adventure based on how your class has performed on past skills from the transformation lessons.

To begin, explain to students the setup of functions. At the top of the starter code, begin by setting up an empty function, explaining each piece, like so:

```python
#Write your functions up here!
def happyFace():
    #your function here
```

In Python, it's important that both variables _and_ functions are declared or defined before they are used. That means it's usually safest to do them at the top of your code to keep things organized - you can even mark in comments where your variables and where your functions are living.

From there, take the code for the happy face - lines roughly 15-21 - and copy/paste them into the function. Remove them from the `draw()` function so you have something that looks like this:

```python
from processing import *

#Write your functions up here!
def happyFace():
    strokeWeight(1)
    stroke(0)
    fill(169, 222, 183)
    ellipse(125,200,100,100)
    arc(110,200,25,25,radians(180), radians(360))
    arc(160,200,15,25,radians(180),radians(360))
    arc(136,226,40,10,radians(0), radians(180))


def setup():
    size(400,400)


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    #Happy Face
    
    
    #Angry Face
    noStroke()
    fill(235, 161, 70)
    ellipse(275,200,100,100)
    strokeWeight(2)
    stroke(0)
    line(270,196,289,183)
    line(254,196,237,188)
    strokeWeight(1)
    arc(284,200,25,25,radians(0),radians(180))
    arc(261,232,20,40,radians(180),radians(360))
    arc(245,200,15,25,radians(0),radians(180))


draw = draw
run()
```

Students have been working in python for awhile, but make sure they understand that indentation _matters_ and that they just indent with the same characters (space or tabs) and same amount of characters each time. Everything indented under the `def happyFace():` line is considered a part of that function!

Students will notice that the happy face has disappeared. Explain that now the function has been DEFINED, you can CALL it in the draw function. In the draw function, write `happyFace()` below the comment so it reappears. This may not seem super impressive to students - it’s where they started, after all - but the benefit of this method is that now they can make MANY happy faces. Ask students how they could make more and prompt them to the idea of writing the function call several times if needed. They will notice a problem - there is still only one happy face. Ask students why this is - many will realize it’s because it is drawing at the same place every time.

This is your chance to choose a code along path that is most sensible to your students from the options below!

#### Option A (recommended):&#x20;

* Students will create parameters for x and y&#x20;
* Students will use this x and y to control the positions of each shape, adding and subtracting to keep the distances correctly related to each other.
* _This is an easy and direct approach for students who may not have felt comfortable working with push(), pop(), and translate()._

```python
#Final Product
def happyFace(xPos, yPos):
    strokeWeight(1)
    fill(169, 222, 183)
    ellipse(xPos,yPos,100, 100) #125, 200
    arc(xPos-15,yPos,25,25,radians(180),radians(360))
    arc(xPos+35,yPos,15,25,radians(180),radians(360))
    arc(xPos+11,yPos+26,40,10,radians(0),radians(180))
```

**Option B:**

* _This option will require you to do an advance preview of transformations specifically `translate()`, `pushStyle()`, and `popStyle()`. They are relatively low lift, but anticipate it will take an additional 10-20 minutes to explain. It may confuse students still struggling with the coordinate system._
* Students will create parameters for x and y&#x20;
* Students will use this x and y to control the translation of the shape, and will rewrite the shape to draw from 0.&#x20;
* Be sure to include a push and pop so the translation only applies in the function!

```python
#Option B Final Product
def happyFace(xPos, yPos):
    pushStyle()
    translate(xPos,yPos)
    strokeWeight(1)
    stroke(0)
    fill(169, 222, 183)
    ellipse(0,0,100, 100) #125, 200
    arc(-15,0,25,25,radians(180),radians(360))
    arc(35,0,15,25,radians(180),radians(360))
    arc(11,26,40,10,radians(0),radians(180))
    popStyle()
```

**Option C**:

* In this option, start with Option A, and then ask students to scan the reference sheet for something that would make moving many shapes easier. Once they get to translation, revise the function.
* This would also be a terrific second-day activity or something to bring out as an extension when students work on the mini-project.

Once students have a working function and can use the function call several times to draw many smileys, ask them what else they may want to change about the smiley. Rather than coding that in now, ask them to include comments to come back to later.

### Independent Practice: Angry Face (\~10 minutes)

Explain to students that they will now practice what they’ve learned by turning the angry face into a function. You can choose to have students work alone or to pair program. If they are pair programming, have them swap after each 2-3 steps/new lines of code!

### Wrap-Up (\~5 minutes)

Time permitting, consider having one or two students share their solutions with the class, or having students feeling stuck share their non-solution to get feedback from the class.

You may want to collect their work (via Google Form or similar) to review the functions they have written as an exit ticket. Consider having them add any questions they still have as comments before submitting!

### Extensions

_**After this lesson, students will be creating functions of their own unique designs. Encourage students to try for the most efficient way to write their functions now, and if they need more to do, ask them to review a previous design - like the taijitu symbol - and turn it into a function.**_
