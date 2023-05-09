---
description: How can I use Classes, lists, and for loops to generate many objects?
---

# U4LA3.1: Creating Many Objects

### Teacher Notes and Overview

In this lesson, students will combine things they have been learning in Unit 4 with prior skills form Unit 3 to create a class and generate _many_ objects. They will have exploratory time to add more functions to these many objects and experience how powerful Classes and objects can be at this scale.

### Objectives

Students will be able to:

* Save objects in a list
* Utilize for loops to generate many objects
* Utilize for loops to execute methods on objects in a list

### Suggested Duration

\~1 Period (45 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

_No new vocabulary is introduced in this lesson_

### Planning Notes and Materials

|                    Planning Notes                    |                        Materials                       |
| :--------------------------------------------------: | :----------------------------------------------------: |
| There are no specific planning notes for this lesson | There are no specific materials needed for this lesson |

### Resources

* [Starter Code](https://trinket.io/library/trinkets/0c43613db2) (Trinket)
* NEED PYTHON VIDEO

### Assessments

**Formative:**

* Creation of Bubble Class and student challenges

**Summative:**

* Upcoming Mini Project (Optional)
* Upcoming End of Unit Project

### Do Now/Warm Up (7 - 10 min)

Create a Bubble class that will contain all necessary properties to draw a moving Bubble (ellipse). It should also have methods to display, move (smoothly - no more random!), and bounce on edge.

If you finish early, consider styling your bubble, perhaps by making it slightly transparent so it's more bubble-ish.

### Make Many Bubbles Code Along (15 - 25 min)

As students complete their warm up, bring them back together and make sure you are all on the same page and have a working class. You may want to have everyone utilize the [Starter Code](https://trinket.io/python/0c43613db2) (Trinket) o make sure things work, or simply display the code and allow everyone to make edits so they have a Class that creates functional objects:

```python
class Bubble:
  def __init__(self, d):
    self.x = random(width)
    self.y = random(height)
    self.diameter = d
    self.xSpd = random(-3,3)
    self.ySpd = random(-3,3)
  
  def display(self):
    fill(255, 255, 255, 50)
    stroke(255, 255, 255)
    strokeWeight(2)
    ellipse(self.x, self.y, self.diameter, self.diameter)
  
  def move(self):
    self.x += self.xSpd
    self.y += self.ySpd
  
  def bounceOnEdge(self):
    if self.x > width - self.diameter/2 or self.x < self.diameter/2:
      self.xSpd *= -1
    
    if self.y > height - self.diameter/2 or self.y < self.diameter/2:
      self.ySpd *= -1
  
  def animate(self):
    self.display()
    self.move()
    self.bounceOnEdge()
```

Once everyone is on the same page, create a single object and test that everything is working according to plan:

```python
from processing import *
from collide2d import *
from classes import *

def setup():
    size(400,400)
    global bubble1
    bubble1 = Bubble(30)
   

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    bubble1.animate()
    

    
draw = draw
run()
```

Then, explain to students that we are going to learn to make _many_ bubbles on our canvas. This can be a confusing concept - right now, students just know that they would need to make many variables, and we haven't actually learned of a method that will automatically create new and named variable instances for us.

Instead, our solution is going to be to create our objects and load them into a list! Our empty list has infinite space to store objects, and we can use for loops to populate our list and to make our newly created objects function with methods on the canvas.

To start out, we need an empty list - let's call it `bubbles`. For the sake of readability, we will be deleting our one functional bubble for this lesson, but you can encourage students to simply comment it out.

```python
bubbles = []

def setup():
    size(400,400)
   

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    

    
draw = draw
run()
```

Now it's time to make our for loop. This loop is going to control how many Bubbles we put in our list  - we will do this in setup to make sure the bubbles are just created once and exist by the time we get to draw:

```python
from processing import *
from collide2d import *
from classes import *

bubbles = []

def setup():
    size(400,400)
    global bubbles
   
    for num in range(10):
      bubbles.append(Bubble(30))


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    

    
draw = draw
run()
```

If we do `print(bubbles)`, we will see we have a list of all our Bubble objects. But just as in our Wiggler project, nothing is on our screen yet because we haven't told them they are supposed to be!

Let's head down to the draw function. We can use another for loop here to make things start happening on our canvas:

```python
from processing import *
from collide2d import *
from classes import *

bubbles = []

def setup():
    size(400,400)
    global bubbles
   
    for num in range(10):
      bubbles.append(Bubble(30))


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    for bubble in bubbles:
      bubble.display()
    
draw = draw
run()
```

This for loop is iterating through our entire list, as we've seen in other projects, and for each bubble in the list, it's displaying the bubble. Note that we could also use 'for in range' to accomplish this task, but it would be a little more convoluted than iterating directly through the list objects! We could also add our other methods to this single for loop:

```python
from processing import *
from collide2d import *
from classes import *

bubbles = []

def setup():
    size(400,400)
    global bubbles
   
    for num in range(10):
      bubbles.append(Bubble(30))


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    for bubble in bubbles:
      bubble.display()
      bubble.move()
      bubble.bounceOnEdge()
    
draw = draw
run()
```

We can, of course, also just use our `animate()` method, but it's important for students to see and understand that they can call multiple methods in a single for loop. You may want to demonstrate to students how easily they can use this method to make significantly more than 10 bubbles - have them try to make 100 by adjusting the for loop in the setup function and see what happens!

### Student Exploration (15 - 25 minutes)

Give students options to continue working with their many objects! They may choose to:

1. Return to the random wiggler - make many in different colors that spread across the screen.
2. Create a method so the bubbles change color when they bump into each other (will need to link Collide2D if not using the starter code)
3. Create a method so the bubbles bounce off each other when they bump into each other (will need to link Collide2D if not using the starter code)
4. \[**Spicy**] Recall what you learned about arrays. Can you create a method that can be used in `function mousePressed()` so that a bubble is deleted from the array - and thus the canvas - when clicked?

### Wrap-Up (5 minutes)

You may want to have students display what challenges they succeeded in or discuss sticking points. You could also have them respond to any of the following, either via discussion or written response:

1. Think back to past projects - where did you experience many things that could've been better off as an object?
2. How do you think you will use these skills in future projects?
3. What was challenging about making numerous objects?

### Extensions

Ask students to try to make another useful class and create many of the objects on the screen!
