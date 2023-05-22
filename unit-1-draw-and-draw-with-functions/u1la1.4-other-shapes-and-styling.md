---
description: How can we use shape functions to create images?
---

# U1LA1.4: Other Shapes & Styling

### Teacher Notes and Overview

In this learning activity, students will explore the various Processing.py shape-drawing functions as pairs or in groups. The second focus of the lesson will be building research and collaboration skills so that students can have a successful time when programming in Processing.py. Then they will continue to build on their understanding of functions and their parameters to recreate the pre-determined shapes and designs.

This lesson is an exploratory lesson meant to help empower students with the ability to troubleshoot problems when coding. They will be heavily using the Processing.py reference website, so make students are pair programming efficiently. Some students will struggle with researching on their own so it is important to tell them that a programmer is not able to remember every function but should be able to read and use them.

### Objectives

**Students will be able to:**

* Consult the Processing.py reference for documentation
* Utilize the reference sheet to create triangles, quadrilaterals, arcs, and shapes defined by their vertices.
* Style shapes with `fill()`, `stroke()`, and `strokeWeight()` functions

### Suggested Duration

\~1-2 periods, 45-90 minutes

_This timing will depend on how comfortable with documentation and coding your students are - if they have a lot of prior experience, this lesson could easily be abbreviated to a single period. For students new to CS, allow more time to build this base of exploration._

### NYS Standards

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **Function** - Functions are lines of code that perform specific tasks.
* **Parameters** - Parameters are the values inside of parenthesis following the name of the function.
* **triangle() -** function that draws a triangle by taking in six numeric values which each represent an (x, y) coordinate of a vertex
* **quad() -** function that draws a quadrilateral by taking in eight numeric values wihch each represent an (x, y) coordinate of a vertex
* **beginShape() -** a function that works with **vertex()** and **endShape()** to define a shape or polygon by an unspecificed number of verticies
* **arc() -** a function that draws a piece of a circle by taking in a minimum of six numeric values that control, in order: the (x, y) coordinates of the center of the circle the piece is cut from, the width/height of said circle, and the radian or degree measures of where the piece stops and starts. Optionally, it can take in a final value that determines the style the arc is drawn.

**Pre-Req Vocab:**

* **Vertices** - a corner or a point where lines meet.
* **Quadrilateral** - A four sided polygon.
* **Triangle** - Three sided polygon

### Planning Notes and Materials

|                                                                               Planning Notes                                                                               |                                                                    Materials                                                                    |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------: |
| Arcs may or may not require special attention, depending on the math/geometry skills of your students, and if they have encountered the unit circle yet. Plan accordingly! | <p>p5 Reference Sheet Worksheet (printed)</p><p></p><p>You may want extra print-outs/diagrams/chart paper to explain arcs and unit circles.</p> |

### Resources

* [Basic Shapes Reference ](https://drive.google.com/file/d/0Byk7AxhPkTEJWWdUeVFteXFrT2M/view?resourcekey=0-9VnPTi4HT8fBU7uDd065lg)(Written for p5.js, but many key components are the same)
* [Processing.py Reference Sheet](https://py.processing.org/reference/)
* [Blank Reference Sheet Worksheet](https://docs.google.com/document/d/1DQvWNCJaGxc90KLN7ohWrHnh7jJdCHb1WPdplc2NcuA/copy)
* [Blank Project w/ Coordinate Text](https://trinket.io/library/trinkets/db10a38077) (Trinket)
* Styling Shapes (MAKE VIDEO) | [Starter Code](https://trinket.io/python/79ede85278) (Trinket)

### Assessments

**Formative:**

&#x20;Verbal responses during the **do now** discussion.

p5 Reference Sheet Worksheet answers

Code Challenges

**Summative:**

Taijitu Symbol Mini Project (Upcoming Mini Project)

Abstract Album Art (End of Unit Project)

### Do Now/Warm Up (\~3-5 mins)

**Ask students to respond to:**

1. What do you do when you are stuck or confused on a problem?
2. How do you think a software engineer solves a problem when they are stuck or confused?
3. How does risk-taking play a role in problem-solving? Give examples using our classroom.

_After students have answers, having an open discussion on these questions is a good way to gauge the temperature of the classroom. Students should know that a programmer does not know everything but they have them collaborate and research skills to find creative solutions._

_You may want to expand the conversation with these optional questions:_

* How can we promote self-advocacy?
* What are successful peer collaboration skills?
* What would help you as a student to be able to search for solutions?

_Creating a poster from students' feedback can help create a successful and safe risk-taking culture in your classroom._&#x20;

_Interesting Video on Tech Culture:_ [_https://www.youtube.com/watch?v=QW834PGYnYI_](https://www.youtube.com/watch?v=QW834PGYnYI)

### Introducing: The Reference Sheet (\~20 - 30 min)

Explain to students first that they will be doing an activity that will have them researching and problem-solving with their peers - hence the starter activity. If you have not, segue the Do Now conversation into a list of things students can do when they are stuck. Let students know today is their first day to practice being stuck and getting unstuck! An example list is as follows:

* _**Ask yourself:**_
  * _What was supposed to happen?_
  * _What happened instead?_
* _If there is an **error message** look at the line number and error description. If the error message has a suggestion try that first._
  * _In Trinket, use the arrow next to the play/stop button and select 'console' to see more detailed errors._
* _Check for **common errors** working line by line from top to bottom_
* _**Play** with the code. Make one change at a time then hit run._
* _**Use teamwork.** Compare your code to the code of someone next to you._
* _**Check out the Processing.py online reference.**_ [ ](https://py.processing.org/reference/)[_https://py.processing.org/reference/_](https://py.processing.org/reference/)
  * _Model how to navigate the reference guide and then how to read the arguments a function takes._
* _**Attach a sticky note to the back of your laptop.** Let your peers or teachers know that you need extra help._

We said reference guide, but we haven't actually looked at the reference guide yet, so let's start there today. You'll begin by showing students their way around the reference sheet page:

<figure><img src="../.gitbook/assets/Screen Shot 2022-09-28 at 3.06.37 PM.png" alt=""><figcaption><p>Screenshot of the main page of the Processing.py Reference</p></figcaption></figure>

Distribute the [Processing.py Reference Sheet Worksheet](https://docs.google.com/document/d/1DQvWNCJaGxc90KLN7ohWrHnh7jJdCHb1WPdplc2NcuA/edit). Although triangle is filled out, use that as a starting place to navigate the online reference sheet - show them how they would find the function, read the reference, and even test adjusting coordinate values to change the sample shape. Once students are comfortable, give them \~10 more minutes to work through 'line' on the worksheet. Circulate to answer questions, troubleshoot, and play as students explore.

Once they have previewed several functions, ask them to recreate something similar to the following:

<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption><p>Four shapes on grey background, a triangle, a star-esque polygon, a quadrilateral, and a small arc.</p></figcaption></figure>

[Possible Solution](https://trinket.io/python/13becd8fde)

While they shouldn't hurt themselves trying to get everything EXACT, their sketches should include:

* Sketch name that matches the unit and lesson number. Make this a standard practice in your classroom.
* A canvas size of 600 pixels wide by 120 pixels high.
* Light gray background.
* One of each of the following shapes: triangle, polygon, quadrilateral, arc (the arc is an extra spicy challenge).

Circulate the room to ensure students are adding comments to their code to label each shape.

For students choosing to create the star shape or their own polygon, remind them that they can use the beginShape() function, and then add as many vertices as needed. Add endShape(CLOSE) at the end to close the shape.

### \[OPTIONAL] All About Arcs (\~10-12 minutes)

While some students will deduce how to create arcs from the reference sheet, many will struggle because arcs a) require a LOT of arguments and b) are meausred in radians by default, which most students will not see until Algebra 2/Pre-Calc. It may be worthwhile to call students back together for a mini-lesson on arcs after they've experienced the triumph of making triangles, quads, polygons, etc from the reference sheet!

Begin by explaining that an arc is a piece of a circle. When we deal with arcs in Processing.py, this is what the computer expects to get:

`arc(x, y, width, height, start, stop)`

Now, these first four values should look familiar: that's all the same as an `ellipse()` that they have been dealing with for a few lessons, now. This is the circle that they will be cutting a piece out of. The final two arguments, the `start` and `stop`, refer to where you are cutting the circle to create your arc.

In Processing.py, these are radian measurements. If you are comfortable and would like to offer a supplementary math lesson, you can feel free to discuss the unit circle with students and explain that degrees, specifically the 360, are an arbitrary measurement that was chosen because it divides nicely. Angles can also be measured in radians and circles contain 2π radians. Radians are more specific and precise, which is why our code defaults to them. That would be the spicy, advanced option for this optional section.

If your students get overwhelmed, you can take it a notch down, paraphrase everything happening above, and explain that although computers like precise radians, we can either a: use the unit circle to identify the radian measures we need or b: utilize a degree to radian calculator to help us input less precise (read: terminating) values of Pi. If you google **'degree to radian calculator,'** you'll get the easy built-in-to-Google version for your use.

Additionally, Processing.py has a function called `radians()` that will take in a degree measure and return a radian measure. If you wanted, for example, a half circle from 0 to 180, you would write `radians(0)` and `radians(180)` in your arc function.

Either way, displaying a unit circle that also shows degree measurements will be helpful in your cause:

<figure><img src="../.gitbook/assets/image (1) (2) (1).png" alt=""><figcaption><p>Unit circle displaying radians and degrees</p></figcaption></figure>

Students intent on always using the calculator can benefit by looking up circle degree images, which can help them decide which values to put into the calculator to make things start/stop differently.

Your code would look like this if you wanted to draw, say, a half circle using radians:

```python
from processing import *

def setup():
    size(400,400)

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    arc(200, 200, 100, 100, 0, PI)
    
    
draw = draw
run()
```

And like this if you wanted to draw a different arc that will convert your degrees to radians:

```python
from processing import *

def setup():
    size(400,400)

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    arc(200, 200, 100, 100, radians(90), radians(270)
    


draw = draw
run()
```

As a note, arcs in Processing.py will only draw if the radians go from lower to higher radians/degrees. You will sometimes want arcs that present differently than say, 0 to 180 - if you wanted to go from 180 to 0, you would instead need to say 180 to 360, as 0 and 360 are the same place on the circle, but 360 is a higher value.

Ask students to try to create a few more arcs before you move on to the next section. Arcs will make the next mini project infinitely easier!

### Styling Shapes (\~15 - 20 minutes)

We can now make many shapes, but they all look fairly plain, so it's time to give them some style! Give students about 5-7 minutes to go into the reference sheet and find definitions for `fill()`, `stroke()`, and `strokeWeight()`. Once they're done, it's time for a code along.

Ask students to duplicate/fork the [starter code.](https://trinket.io/python/79ede85278) Begin by demonstrating fill() and changing the first shape to black:

```python
fill(0)
ellipse(30, 45, 35, 35)
```

Important to note for students is that we have to style the shapes _before_ we draw them because the computer is going to run our code in order. They'll notice that even though we put `fill(0)` above the ellipse, it has changed the fill of ALL shapes. This is because we did not give them different fills! Add a fill above the next shape to demonstrate that it will now have its own color.

Then, take a moment to demonstrate `stroke()` and `strokeWeight()` in the same way. Recall that stroke changes the color of the outline, while strokeWeight adjusts the thickness of the outline. Like fill, they will apply to all shapes, so it is important that each shape has its own `stroke()` and `strokeWeight()`. After the ellipse and rect are styled, students can either individually or pair program style for the rest of the shapes on the page.

One thing that students may notice is that the helper coordinate text is getting styled, too, and may become distracting or unreadable. This is because the draw function runs on a loop, meaning whatever the last styling text is will loop back up to the top and apply to whatever comes first if it is not otherwise styled. Ask students if they can figure out a solution, and they should come up with something like this:

```python
strokeWeight(1) //alternately, they may use noStroke()
stroke(0)
fill(0)
text(str(mouseX) + ", " + str(mouseY), 20, 20)
```

**NB:** _To focus the instruction a bit, we aren't worrying about color. Some students may figure it out - that's just fine! We will talk more about it in later lessons, but encourage black and white just so they don't get fixated on making things pretty quite yet._

### Wrap Up (5 min)

Ask 2-3 students to share their code examples. Students should share their project link with teacher prior to answering and explaining how they created their shapes.

**Ask Students:**

* What are the benefits of displaying mouseX and mouseY on the canvas? How can it be used for future projects?
* What was challenging when drawing more complex shapes or styling shapes?
* What are the things important when drawing more complex shapes or styling shapes?

### Extensions

Ask students to create and style some more advanced, specific shapes, such as:

<figure><img src="https://460882682-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F6CpkJAKaYOwA5TCz4W7l%2Fuploads%2FRV9Yxt8eVmD7pNeRM2un%2Fimage.png?alt=media&#x26;token=e5a0beca-ec36-4e1b-89f6-ad4aa8a027ec" alt=""><figcaption><p>Traditional outline of a house using the beginShape() function</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption><p>3/4 circle using arc function</p></figcaption></figure>
