---
description: How do the parameters of function effect positioning on the p5 canvas?
---

# U1LA1.2 Line Functions and Parameters

### Teacher Notes and Overview

In this learning activity, students will create a visual composition using the Processing.py shape-drawing functions point() and line(). They will be introduced to functions, parameters, and then how to call them in Processing.py.

Students should have already created an account and know how to log in. If not it would be good to model it before reviewing the editor.

This lesson will be the first time that many students will be coding along with the teacher; give students enough time to copy as they get accustomed to code-alongs. Giving students access to the slide deck will help with questions, sharing links, and entry points for anyone who may have gotten off track or needs help.

### Objectives

Students will be able to:

* Understand the Processing.py canvas coordinate system
* Consult the Processing.py reference for documentation
* Create a line and point
* Change the grayscale value of a canvas
* Use lines to create a rectangle or a house

### Suggested Duration

1 Period (\~45 minutes)

### NYS Standards

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **IDE -** Integrated development area or IDE is a software application that provides a place for computer programmers to develop code.
* **Function -** Functions are lines of code that perform specific tasks.
* **Parameters or Arguments -** are the values inside of parenthesis following the name of the function. These are used to change the outcome of a function

**Pre-Req Vocab:**

* **Width -** Horizontal distance of a 2D shape
* **Height -** Vertical distance of a 2D shape
* **Cartesian (Coordinate) Plane -** four-quadrant grid with an x && y-axis, origin, etc.
* **Vertices -** a point where two or more lines meet

### Planning Notes and Materials

|                                                                                                                                                                                                           Planning Notes                                                                                                                                                                                                          |                                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | ----------------------------------------------------------------------------------------------------------- |
| <p>You’ll be using the online IDE A LOT - make sure every code example linked in your lesson is updated and usable</p><p></p><p>Students should log-in to their account at the beginning of each class (build this as a routine in your classroom)</p><p></p><p>Students will need 3 tabs open for every lesson of this course<strong>:</strong> their IDE, the Processing.py referene sheet, and the slide decks (optional).</p> | <p>Line Worksheet (printed)<br><br>Pens/Pencils<br><br>Highlighters (optional)<br><br>Rulers (optional)</p> |

### Resources

* [Processing.py Reference Sheet](https://py.processing.org/reference/)
* [Line Worksheet](https://docs.google.com/document/d/14mDvlCxeFW6elTAi1RMNdzJZv0ZZVKv3HXlK8hRfNOk/preview)
* [Simplified Blank Editor w/ Text Coordinates](https://trinket.io/python/db10a38077) (Trinket.io)
* Basics of Drawing (NEED TO CREATE PYTHON VERSION)
* (Optional) [Desmos Coordinate Grid Activity](https://teacher.desmos.com/activitybuilder/custom/5f73248eba4291305a86cf50)
* (Optional) [Desmos Coordinate Grid Tool](https://www.desmos.com/calculator/o75y8av9jw)

### Assessments

**Formative:**

**Summative:**

* Taijitu Symbol (Upcoming Mini Project)
* Abstract Album Art (End of Unit Project)

### Do Now/Warm Up (\~3-5 min)

This unplugged activity will help reinforce your student’s understanding of the p5.js coordinate plane. Students can work as groups, pairs or individually.

**Ask students to:**

* Take a [Line Worksheet](https://docs.google.com/document/d/14mDvlCxeFW6elTAi1RMNdzJZv0ZZVKv3HXlK8hRfNOk/edit?usp=sharing)
* List the starting and ending points of each line using the p5 coordinate plane.
* The first point is on the left and then the second is on the right.

_**Once students have finished the task, ask:**_

1. What would be different if these lines were to be drawn on a regular cartesian plane?
2. What are the coordinates for lines 1 - 6?

### Web Editor Overview (\~5-7 min)

It’s up to you if you would like to run this session as a code along, or if you would like to have students clamshell their computers and simply watch. Decide based on what you know of your class and their ability to pay attention! In either situation, if possible, provide steps on a slide deck for any student who may miss steps.

Begin by reviewing how to log in and navigate Trinket. Share students on [this starter code](https://trinket.io/python/db10a38077?runMode=console) which they will be starting most projects from. (It will be useful if you can share the link somewhere like Google Classroom or a similar LMS so they always have access.) Direct students to hit the 'Remix' button, which will create a copy for them. Students should update the name to something related to what they are working on: this one can be **Unit 1, Lesson 1.2 Lines and Points**.

Be sure to demo saving in the Trinket editor - always foreign to students who didn’t grow up with Clippy - and how to open saved files. Additionally, you might show students how to find and organize their Trinkets into folders.

Remind students that having a user account will allow them to save their projects and share them on the web.

Review the main parts of the IDE. If students have not logged in, when you are finished ask students to log in to their accounts.

Once students are logged in, continue to the next section.

### size() and background()

Introducing functions and their parameters for the canvas will be the students' first code alone so some students may ask you to repeat a step or to zoom in on sections of code - make sure you've made the text in your editor quite large to start!

Start by adjusting the values within `size`, hitting run each time. Once you've done it a few times, allow students \~20-30 seconds to experiment on their own. **Then ask:** _What do you think this function does? What do these numbers control?_

Once students have answers that they control the _size_ _of the canvas_ - specifically width and height of the canvas - add a code comment using #. It may look something like this:

```python
size(400, 400) #adjusts width, height of canvas
```

Then, move on to the `background` and similarly adjust the value within the `()`. Repeat the process of exploration before **asking:** _What do the numbers in the background function control?_

Students may not recognize that the `background()` function numbers must be in a certain range - if you go to high it will always be white, and negative numbers will always be black. Explain that this is taking a color range from 0 - 255. Again, teach students to leave a comment such as:

```python
background(220) #The num controls color, 0 - 255
```

This visual may help students in understanding background colors:

<figure><img src="../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption><p>A scale going from black (0) to white (255) with number values marked in between.</p></figcaption></figure>

Make sure students understand that they've been assessing _functions_, which are the words with () after them. Different functions will accept different _arguments,_ which fulfill _parameters_ to make them behave differently. Not all functions accept the same arguments!

Another **important note** since you're working in Python is that students should notice that all of the functions they've been altering so far are _indented_ underneath the function - setup or draw- that they belong to. This is how Python determines what things belong with - or inside - of what, and will be important to us throughout the year!

If time permits, you may start to grow student thinking by **asking:** _What do you think would happen if I add another background?_

Add another background of a color directly below the first - you should only see the last typed background. This is because the code runs in order, top down, which means it is making both backgrounds - but the last one typed is 'painting over' the previous one(s). Students will explore this idea of order more in later lessons.

### Line & Point Function Code Along (5 min)

For this code along it is important to spend time reviewing how the canvas works in p5 and its differences from a cartesian plane. Students can copy these functions and their definitions into a journal. A good practice is to hang posters around the classroom every time a new function is added. Recreate the following Example ([trinket](https://trinket.io/library/trinkets/6905cd697f)) with your students:

```python
from processing import *

def setup():
    size(400,400)

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    #Code-Along: Create a point with x value 110 and y value 80.
    point(110, 80)
    
    #Code-Along: Create a line from point (300, 20) to (400, 100)
    line(300, 20, 400, 100)
    
    

#Do Not Delete!
draw = draw
run()
```

Begin by explaining that you are going to draw a `point()` and a `line()` on the screen. (Beware - points are hard to see without changing `strokeWeight()`, so students may need to do some squinting on their own screens!) We don't know much about Processing.py yet, but luckily, there is a resource to help us.

Direct students to the [Processing.py reference sheet](https://py.processing.org/reference/) and start by looking up points. Review how we know what to type in our own code, and ask students how many arguments and what sort of arguments we need to create a point. Once they have an idea, take some values and create one together.

As you create, be sure to leave comments. Consistently model how to create and utilize comments so students can build great habits of annotating their code! This is a great practice for debugging, testing new code, temporarily blocking out old code, and generally keeping track of what they're doing.

Next, tell students you want to draw a line. Go back to the reference sheet and again **ask:** _What arguments/parameters does a line function need in order to work? What are values I could use to draw a test line?_

Draw one line together and label with a comment.

### Student Activity Practice

Once students are comfortable in the code along, they will be trying to recreate the lines from their worksheet as a python sketch.

**Ask students to complete the following exercises in their editor - it can be the same Trinket from the code along:**

1. Code the lines they found on their worksheet, leaving a comment for each one, and then:
2. Draw a point near the top-right corner of the canvas.
3. Draw a point in the middle of the canvas.
4. Draw a point near the bottom-left.
5. Draw a horizontal line, a vertical line, a diagonal line.
6. Draw a line from the top-left corner to the bottom-right corner.

Use the wrap-up section to have display students' work and for peer feedback.

### Wrap Up

Bring students together to discuss successes and sticking points from the line() and point() practice. Have students come up to the front and live code the lines that they deconstructed from the do now activity.

Student share-outs are a powerful way to build community and promote student ownership of learning. _One approach could be creating a “sharing calendar” where 1-2 students share daily on a rotation (once the whole class has gone, shares start over again)._

Students should share struggles or strengths, and can either a) ask the class for help when sharing or b) share something helpful they learned with the class. Aim to be a teacher facilitator and allow the class to coach itself.

If you want students to share consistently, be sure to plan to hold mini-conferences with students the day they share prior to sharing. This can help them pinpoint something they would like to say or share.

### Extensions

_**For students that finish early, ask them to:**_

* Check that their code has comments so that they can pick up their work from wherever they left off.
* Use multiple line functions to create a rectangle and a triangle so the lines create a house (pentagon).
* Add comments for each line position.

_**For classrooms in need of extra help**:_

Consider utilizing the optional Desmos activities to better familiarize students with the canvas.
