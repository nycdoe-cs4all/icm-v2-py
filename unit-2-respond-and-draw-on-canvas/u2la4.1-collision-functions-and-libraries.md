---
description: What visual cues tell me where my mouse is?
---

# U2LA4.1: Collision Functions and Libraries

### Teacher Notes and Overview

**NB:** _The JavaScript version of this lesson utilizes an external library called Collide2D - we have remade a simpler version in Python for student use. Please note it is not as expansive, but it will get the job done!_

In this learning activity, students will explore creating a function that returns a boolean value to decide if we are on top of a rectangle or not. They will then explore linking another library (Colilde2D) into their program and will explore reading the documentation to complete a series of challenges.

At this point, students have seen mouseX and mouseY and should understand that they hold a changing value. This is theoretically enough to get through the Do Now - however, if students are still struggling greatly (with hints!) after 5 minutes, you can turn this into a Code Along. It’s also recommended students work with partners during the Do Now.

It is up to you to decide if you would like this activity to be pair programmed or done individually.

### Objectives

Students should be able to:

* Understand that conditionals can tell us if the mouse is touching a shape&#x20;
* Utilize the collide2D Library&#x20;
* Use conditionals and functions containing conditionals to create hover reactions

### Suggested Duration

\~2-3 Periods (45 minute each)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.8** Develop a program that effectively uses control structures in order to create a computer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* Hover - when the mouse cursor is moved over an object&#x20;
* Hover reaction - something the object does in response to the cursor being moved over it&#x20;
* Collide2D - a library of boolean functions that check if shapes are colliding&#x20;
* User experience - peoples’ attitude**s** and feelings about using a product or project

### Planning Notes and Materials

|                                                                                                            Planning Notes                                                                                                            |       Materials      |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :------------------: |
| <p>These lessons involve using an external library; you can certainly teach these lessons without, but it does become more difficult.</p><p></p><p>Make sure you have reviewed and understand using Collide2D before the lesson!</p> | Chart paper, markers |

### Resources

* [Collide2D Library \[PY\] Documentation](https://github.com/cmorgantywls/collidewithprocessingpy) | Blank Sketch w/ Collide2D Linked ([Trinket](https://trinket.io/python/d30c563050))
* NEED VIDEO FOR COLLIDE2D WITH PYTHON
* Hover Reaction Starter Code ([Trinket](https://trinket.io/python/f343d479e6))
* Hover on Shapes Starter Code ([Trinket](https://trinket.io/python/9eee468991))
* Extra Practice Starter Code ([Trinket](https://trinket.io/python/3953245969))

### Assessments

**Formative:**

* Hover Reaction Practice Code
* Hover On Shapes Practice Code

**Summative:**

* Lightswitch Game (Upcoming Mini Project)
* Interactive Drawing Tool (Upcoming Unit Final)

### Do Now/Warm Up (3-5 minutes)

Using Processing.py Coordinates, draw the following on graph paper:

`rect(100,150,200,50)`

Then identify as many points (and their coordinates) as you can in the next two minutes that fall inside the rectangle.

### Writing a Collision Function (10 - 15 minutes)

Explain to students that today, you will be focusing on making things reactive when your mouse _hovers_ on, or touches them. This is a common thing students can witness on many webpages and games!

As you review the brain starter, ask students to come up with rules for points (x coordinates and y coordinates) that would tell you they are definitely a point in this rectangle. You may need to draw the rectangle large on the board to help students understand. They should come to the idea that all x points must be between 100 and 300, and all y points must be between 150 and 200. Introduce students to this idea:

<figure><img src="../.gitbook/assets/image (1) (2) (2) (1).png" alt=""><figcaption><p>Image of rectangle showing constraints for x and y coordinates inside of shape.</p></figcaption></figure>

From here, it's time to start coding along. First, have students imagine what this might look like in some basic code:

```python
if mouseX > 100 and mouseX < 300 and mouseY > 150 and mouseY < 200:
    #anything that happens here means you are on rect
else:
    #anything that happens here means you are NOT on rect
```

Now, there are simple things we could do like change the color of the rectangle when we are on it using a variable, or console.log'ing to say that we are over the rectangle.  (You may want to demonstrate BOTH to your students in the code along before moving ahead, so they get the idea of what we're doing.)&#x20;

But what if we are making a program that has _many_ rectangles, and I want my mouse to be able to interact with all of them?

Rather than repeating the same code over and over, it would make more sense to create a function that will just tell me if I am on the rectangle or not. Instead of returning a string that says something like "On rect" or "off rect", this is where we can use our true/false boolean values.

So let's write a test function together! With your students, create something like the following:

```python
def mouseOnRect(x, y, w, h):
    if mouseX > x and mouseX < x+w and mouseY > y and mouseY < y+h:
        return True
    else:
        return False
```

Now, we can put this to use:

```python
#create a variable to control color of the rect, add fill, ensure you have rect from brainstarter drawn.
#and make sure the variable is global use in your draw function!

if mouseOnRect(100, 150, 200, 50):
    rectColor = color(255, 0, 255)
else:
    rectColor = color(0, 255, 255)
```

We are ultimately still using a conditional, but this one contains a shorter boolean expression because that expression is _abstracted_ out into our function. The function is reusable and would work for any other rectangle!

### Meet Collide2D (15-30 minutes)

Now, this is useful, but  it doesn’t account for other shapes - if we wanted to determine if we were over an ellipse (or a triangle, heaven forbid!) we would need to figure out different types of logic. All of this is possible, but perhaps more work than we want to do.

Because of this, we will be using another Python library. This is written in Python but based on a JavaScript library called Collide2D. It works off of Processing.py, but is essentially just many collision functions that have already been defined for us.

Ask students to make a copy of this starter code ([Trinket](https://trinket.io/python/f343d479e6)). Start by showing students the [Collide2D library](https://github.com/cmorgantywls/collidewithprocessingpy) - explain the parts they can safely ignore and the bits they want to read.  Students will want to know how to navigate the table of contents. Once they get there, tell them that you are going to try to decide if the mouse is on top of a rectangle - which code would they want?

Students should land on collidePointRect (the mouse is considered a point). Click on it and explain to students how to read the documentation and do a brief compare/contrast to the function they wrote. They should have an example of how it’s used as well as what goes into the function itself. It’s recommended to copy/paste this function into their code as a comment so they can use it as a reference. Code the reaction to the rectangle so students have something like this:

```python
#collidePointRect(pX, pY, rX, rY, rW, rH)

if collidePointRect(mouseX, mouseY, 20, 50, 110, 110):
    rect1Color = color(100, 200, 50)
else:
    rect1Color = color(50, 100, 200)
```

Once students have completed the code along, give them a chance to finish the rest of the practice activities, as a pair programming challenge or independently. The practice is redundant on purpose, and if students get bored, ask them to try to change other things on the hover reaction instead of just color.

This lesson also offers a good moment to reinforce the objects that they have been working with in the prior lessons. While each individual shape only has one property that is changing, because all of these properties are the same (they’re colors!) this could be a way to group the object. Note that because you are using color declarations, you’d need to declare the variable globally and assign color values in setup before changing them in draw. The declaration and initialization would look something like this:

```python
from processing import *
from collide2d import *

colors = {}

def setup():
    size(400,400)
    global colors
    colors = {
      "rect1":color(255,0,255),
      #add key:value pairs for each shape!
    }
```

They could then use the color in the following way:

<pre class="language-python"><code class="lang-python"><strong>#using a color
</strong><strong>fill(colors["rect1"])
</strong>rect(20, 50, 110, 110)
</code></pre>

And you could update the color like so:

```python
if collidePointRect(mouseX, mouseY, 20, 50, 110, 110):
    colors["rect1"] = color(0,255,255)
else:
    colors["rect1"] = color(255)
```

The big takeaway here is that values grouped in an object should have some commonality between them - either that they are all attributes of the same element, or they are all the same attribute of many elements.

### Collide with Shapes (25 - 35 minutes)

Most likely, this section will be the start of the second day of this lesson cycle. As a launch into it, consider asking students to explore other options in the Collide2D library, or find a common error based on the prior day’s work that you display on the board.

Ask students to duplicate this starter code ([Trinket](https://trinket.io/python/9eee468991)). Then, code along with them the steps to make the strokeWeight of the line increase when the mouse is over the line. _(Note: One oddity about the collidePointLine function is that it has an optional final value. Students have seen optional values before, but this one controls something called ‘buffer’ - explain to students that this is how forgiving/precise you have to be about being on top of the line itself, because lines can be small. Allow for them to play with values between 0 and 1 and test out the varying results!)_

```python
#collideLinePoint(x1, y1, x2, y2, px, py, [buffer])

if collideLinePoint(25, 20, 155, 70, mouseX, mouseY):
    lineWeight = 10
else:
    lineWeight = 2 
```

After this, send students to find the correct collide2D codes to complete the remaining challenges. This can serve as an excellent pair programming activity or can be completed alone, depending on your preference for your classroom and student moods.

### Extra Practice: Puzzle Edition (20 - 30 minutes)

One common misconception that students gain through generalization in these lessons is that when you hover of a shape, that specific shape must be the one to change. In reality, as a programmer you are the one giving instructions to the computer about what should be done - and that means that each shape could be a secret switch to trigger something else to happen. (We will come back to this in the mini-project.)

[Share students on this starter code](https://trinket.io/python/3953245969).&#x20;

Give them 15-20 minutes to complete the following exercise.

Give/display the following instructions (they can be adjusted for level as needed). Use conditionals and variables to make the following things happen:

* When you hover over the top left ellipse, it should turn light blue.&#x20;
* When you hover over the top middle ellipse, the bottom left and bottom right ellipse should turn purple.&#x20;
* When you hover over the top right ellipse, it and the bottom middle ellipse should turn black.&#x20;
* When you hover over the bottom left ellipse, it should turn the entire top row of ellipses red.&#x20;
* When you hover over the bottom center ellipse, it should turn the top left ellipse green.&#x20;
* When you hover over the bottom left ellipse, it should turn the bottom right ellipse orange.

### Wrap-Up (5 minutes)

Students can submit code via a Google Form if you would like to collect it. If not, have students come back together for a discussion on what struggles they encountered in this activity.

### Extensions

Ask students to find a way to keep track of how many times a shape has been hovered on. If it has hovered a certain number of times, make the reaction on hover change.
