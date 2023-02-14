---
description: How can I manage data in my list?
---

# U3LA2.4: Updating and Deleting from Lists

### Teacher Notes and Overview

In this lesson, students will learn to update and delete items from a list as they create a bubble pop game. Depending on future projects, they may use this skill often, or it may be somewhat dormant until Unit 4 - both are okay, as it offers great exposure and rounds out their skills with lists.

### Objectives

Students will be able to:

* Add items to an existing list
* Delete items from an existing list

### Suggested Duration

\~1 Period (\~45 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.7** Design or remix a program that utilizes a data structure to maintain changes to related pieces of data.

**9-12.CT.8** Develop a program that effectively uses control structures in order to create a computer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* `.append()` - add an item to the end of a list
* `.remove()` - remove an item with a specified value.

### Planning Notes and Materials

| Planning Notes | Materials |
| :------------: | :-------: |
|                |           |

### Resources

* [Array Methods](https://www.w3schools.com/python/python\_ref\_list.asp) (W3 Schools)

### Assessments

**Formative:**

**Summative:**

### Do Now/Warm Up (\~5 - 10 minutes)

_Ensure students are working in a new project that has the collision functions added and imported, or be prepared to add/import later in the lesson._

Ask students to create a list that is prepopulated with at least 5 dictionaries that have information to draw an ellipse. They should at a minimum have the x, y, w, h information, and time permitting, have any colors they would like the circles to be.

Encourage students to use the for loops they have learned previously to do this, but if they are feeling stuck, they can do it manually.

### Removing Items from a List (\~15 Minutes)

If students have not already, ask them to use a loop to display the ellipses on their screen. If they are using examples from the previous lesson, they likely will do something like this:

```
from processing import *
from collide2d import *

bubbleList = []

def setup():
    size(400,400)
    global test
    
    for i in range(0,5):
      bubbleList.append({"x": random(width), "y": random(height), "w": 20, "h": 20})
    
  

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    for bubble in bubbleList:
      ellipse(bubble["x"], bubble["y"], bubble["w"], bubble["h"])
    
  
    

draw = draw
run()
```

We now have bubbles on our screen! Let's make them interactive - let's say we want to click on our bubbles, and have them disappear. There are a few ways we can do this: the most basic is to have them move off the screen by changing the x and y values or to make the width and height so small they can't be seen. But there's a better way! _We can remove them from the list entirely._

To do this, **first make sure you have the Collide LIbrary linked in your program.** Then, let's use `mousePressed()` to add interactivity - this is because we only want this to happen once, when we first click our mouse.

Like with displaying all of our circles, we will use another loop here to check if they are being clicked:

```
from processing import *
from collide2d import *

bubbleList = []

def setup():
    size(400,400)
    
    for i in range(0,5):
      bubbleList.append({"x": random(width), "y": random(height), "w": 20, "h": 20})
    
  

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    for bubble in bubbleList:
      ellipse(bubble["x"], bubble["y"], bubble["w"], bubble["h"])

def mousePressed():
  for bubble in bubbleList:
    if collidePointCircle(mouseX, mouseY, bubble["x"], bubble["y"], bubble["w"]):
      print("clicked a bubble")
    
  
    

draw = draw
run()
```

We now have a conditional inside of our loop that is checking to see if each bubble has been clicked, and only when they are clicked, it will display the string in the console. You could also adjust this statement to: `print(bubble, "clicked a bubble")` to also display the dictionary with all the bubble's information, if you'd like the distinction!

So now, let's go about removing those bubbles. Luckily for us, there is a python list method called `.remove()` that will remove the first item in a list with a specified value - in this case, whatever the value of the dictionary is. So, let's try it:

<pre><code>from processing import *
from collide2d import *

bubbleList = []

def setup():
    size(400,400)
    
    for i in range(0,5):
      bubbleList.append({"x": random(width), "y": random(height), "w": 20, "h": 20})
    
  

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    for bubble in bubbleList:
      ellipse(bubble["x"], bubble["y"], bubble["w"], bubble["h"])

def mousePressed():
  for bubble in bubbleList:
    if collidePointCircle(mouseX, mouseY, bubble["x"], bubble["y"], bubble["w"]):
      print("clicked a bubble")
      bubbleList.remove(bubble)
    
  
<strong>    
</strong>
draw = draw
run()
</code></pre>

Now, if they click the bubbles, they should see them vanish as the object gets deleted from the list!

**NB:** _This is a great time to discuss how they could turn this into a function that could be reused. For example, you could walk students through creating a function called `deleteFromList()` that would iterate through a list and delete the given items!_

### Adding Items to Your List (\~10 - 15 minutes)

If we are loving clicking, we may notice that eventually we are out of bubbles and need to get more. While we could click play, that would require the page to reload - what if we don't want to do that? Let's create a button that will make more bubbles for us!

First, let's get a rectangle in our draw function that will display on the screen and can serve as our button:

```
 rect(10, 30, 110, 50)
 fill(0)
 text("MORE BUBBLES!", 15, 60)
```

Now, we are also going to use `mousePressed()` for this - we will just add below the code we wrote to delete our bubbles. Since we have our collision library already linked, we will go ahead and create a conditional for what should happen when the rectangle is clicked.

We will then use the `.append()` method that we saw in earlier lessons to add a new object to our list:

```
from processing import *
from collide2d import *

bubbleList = []

def setup():
    size(400,400)
    
    for i in range(0,5):
      bubbleList.append({"x": random(width), "y": random(height), "w": 20, "h": 20})
    
  

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    fill(255)
    rect(10, 30, 110, 50)
    fill(0)
    text("MORE BUBBLES!", 15, 60)
    
    for bubble in bubbleList:
      fill(255)
      ellipse(bubble["x"], bubble["y"], bubble["w"], bubble["h"])

def mousePressed():
  for bubble in bubbleList:
    if collidePointCircle(mouseX, mouseY, bubble["x"], bubble["y"], bubble["w"]):
      print("clicked a bubble")
      bubbleList.remove(bubble)
    
  
  if collidePointRect(mouseX, mouseY, 10, 30, 110, 50):
    bubbleList.append({"x": random(width), "y": random(height), "w": 20, "h": 20})
    
  
    

draw = draw
run()
```

And tah-dah! Just like that, you are adding elements to a list. Cool, right?

### Student Practice (\~5 - 10 minutes)

Ask students to work in groups to determine how they could make a button that makes _many_ bubbles appear at once, or that can erase bubbles near each other (that's a very spicy challenge).

### Wrap-Up (\~5 minutes)

In whatever way you prefer to collect work, ask students to respond to one more of the following questions:

1. Explain the process of deleting items from an array.
2. Why are for loops useful when working with arrays?
3. How might you use these skills in past or future projects?
