---
description: How can I use built-in variables to create a program that lets the user draw?
---

# U2LA2.1: Draw with Mouse

### Teacher Notes and Overview

The learning activity introduces p5s program flow, demonstrating how `setup()` and `draw()` function. By using Processing.py's mouse position variables and turning off the background function, they create expressive drawing programs. The use of a new data structure, dictionaries, is a way of keeping code more organized so that students do not get overwhelmed.

This lesson is primarily a code-along, as it introduces several new concepts include object literals. Students will be rewarded for sitting through a very teacher-oriented lesson with ample play time and the chance to share and review each other’s work - and object literals, which we will continue using throughout the course, will make life MUCH easier.

### Objectives

Students will be able to:

* Understand how moving `background` out of the draw function allows the user to draw
* Utilize `pmouseX` and `pmouseY` to create something that draws.
* Use object literals to simplify code that involves many variables

### Suggested Duration

1-2 periods (\~45 minutes each)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.7** Design or remix a program that utilizes a data structure to maintain changes to related pieces of data.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary



* **Control flow**: The order in which steps of an algorithm are executed; determined by logical constructs such as IF statements, loops, and calls to other procedures.
* **pmouseX**: The system variable pmouseX always contains the horizontal position of the mouse or finger in the frame previous to the current frame, relative to (0, 0) of the canvas.&#x20;
* **pmouseY**: The system variable pmouseY always contains the vertical position of the mouse or finger in the frame previous to the current frame, relative to (0, 0) of the canvas.&#x20;
* **frameCount**: The system variable frameCount contains the number of frames that have been displayed since the program started.
* **Dictionary**: a comma-separated list of name-value pairs inside of curly braces. (If you’ve worked in other languages, this is like a JavaScript object literal.)

### Planning Notes and Materials

|                                                                                                                   Planning Notes                                                                                                                   |                                                                             Materials                                                                            |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| This may bleed over into two periods with the addition of dictionaries in Python. That’s okay! They will also get MUCH more practice with these as they go through the course, so help them as needed and it will become more intuitive over time. | Only a computer is required, but you may want pads of paper or other wireframing supplies to help students express their ideas if they are struggling with code. |

### Resources

* Lesson Starter Code ([Trinket](https://trinket.io/python/c2a59291d6))
* NEED DICTIONARY VIDEO IN PYTHON
* NEED DRAW WITH MOUSE VIDEO IN PYTHON

### Assessments

**Formative:**

Draw Tool Creation

**Summative:**

Interactive Drawing App (Upcoming Unit Project)

### Do Now/Warm Up (3-5 minutes)

Ask students to recall the difference between the setup() and draw() functions and discuss them with their partner(s).

### Draw with Mouse (10 - 20 minutes)

Start students with the Lesson Starter Code ([Trinket](https://trinket.io/python/c2a59291d6)) which they should duplicate into their own accounts. Structure this section as a code along - ask students to first hit play, and they should notice that something interesting happens.

So far we have been drawing static images: they don't change over time. But one of the exciting things about drawing computationally is that we can make our drawings dynamic: we can have them change over time and respond to what the user does, or to some other kind of input.

You have probably noticed that `setup()` and `draw()` come up repeatedly in the examples. These are both functions, like rect and ellipse, except that instead of calling them, we have been declaring them in our code. Processing.py takes care of calling them for us. In fact, it calls setup once, when our program starts, and then it calls draw once and again, forever (or until we close the sketch window).

To prove it, look at this example. Each time our draw() function is called, Processing.py adds 1 to a variable called `frameCount`. `frameCount` refers to the number of times the draw function reruns (essentially making a new 'frame') which is roughly 60 times per second! In the sketch below, we draw this variable to our canvas, using the text function. As you can see, frameCount keeps growing, as Processing.py calls draw() over and over again.

Now let's get a feel for why frames are important. With your students, remove the background by either deleting it, commenting it out, or moving it to `setup()` where it will only run one time. Before you hit play, ask students what do you they think will happen? Hit play to check if their predictions are true. The could should look like this, and the numbers that were continuously ticking up should still be going up - except now it's on top of each other instead of on top of a fresh background, so it simply creates a blur:

```python
from processing import *

def setup():
    size(400,400)
    background(220)

def draw():

    fill(0)
    text("I'm drawing", 20, 20)
    text(frameCount, 100, 20) #Displays the frame Count
    
    ellipse(300, 80, 10, 10)
    

draw = draw
run()
```

Once students are comfortable with this, explain that when we are not drawing an entirely new background each frame, we actually open up many new creative avenues for ourselves. For example, we can now try moving shapes around the page without a background to get another interesting result.

Although it might seem that our ellipse is only drawn once, it is actually being drawn over and over again for as long as our sketch runs. The reason we don't see any changes is that the ellipse is being drawn, again and again, in the same exact position. For us to see any changes, something needs to vary.

Explain: We have already used mouseX and mouseY in the previous learning activity, to help us place our shapes. Like width and height, mouseX and mouseY are built-in variables. p5 continuously checks where the mouse is and updates mouseX and mouseY with the latest position.

Let's see what happens if we put in `mouseX` and `mouseY` to our ellipse:

```python
from processing import *

def setup():
    size(400,400)
    background(220)

def draw():

    fill(0)
    ellipse(mouseX, mouseY, 10, 10)
    

draw = draw
run()
```

Now let's move our mouse around the page. Since the background only draws once, we now see _every time_ the ellipse gets drawn - and since it follows our mouse position, that allows us to _draw on the screen_ with the ellipse!

Students will notice that as long as we move the mouse at a slow or steady pace, we can get an almost-line (it may be a little bumpy) but if we move it quite quickly, it will look more like separate shapes.

What if we really wanted to draw with one continuous line? This can be tricky, as lines require four coordinate values instead of just the two we used for an ellipse. However, there are two more variables students haven't learned about yet: `pmouseX` and `pmouseY`. These variables hold the position of the mouse in the _last_ frame, and by connecting where the mouse was moments before with where it is now, we are able to create lines.

Our code ends up looking something like this:

```python
from processing import *

def setup():
    size(400,400)
    background(220)

def draw():

    line(mouseX, mouseY, pmouseX, pmouseY)
    

draw = draw
run()
```

### Dictionaries in Python (10 - 20 min)

So we now have something that draws, but it's just something \*really basic\* that draws. Our ellipse and/or line look pretty boring because we are a) just drawing single shapes and b) drawing single shapes without any styling!&#x20;

With students, create a list somewhere in the room of all the things that you could change about this line or another shape (and feel free to get specific - you can change the color or just one value in the color, opacity, etc).&#x20;

Likely, students have made a _really long list._ That means they may be stuck making a lot of variables, and that can be annoying. Luckily, Python and other programming languages have structures built in to handle that! Here, we can use something called a **dictionary**: this is a Python structure similar to an object literal in other languages like JavaScript. A dictionary is really just a comma-separated list of key:value pairs. Each key works a bit like a variable - it holds a value, and can be called by name.

As students have never encountered this before, walk them through how to create an object literal and how they can call values using keys, as in the example below, which you should code along with your students:

```python
from processing import *

theLine = {}

def setup():
    size(400,400)
    background(220)
    
    global theLine
    theLine = {
      "weight":5,
      "red":255,
      "green":0,
      "blue":255,
      "opacity":100
    }
    

def draw():
    global theLine
    
    strokeWeight(theLine["weight"])
    line(mouseX, mouseY, pmouseX, pmouseY)
    

draw = draw
run()
```

**NB:** _As in previous examples, this variable could be given value above setup since it is only using numeric values. However, if students want to use anything Processing.py specific - such as random(), color(), dist(), etc for a value, that would need to happen in setup() or draw(), so it may be easier to demonstrate that protocol from the start with the global keyword, depending on the needs and understanding of your classroom. If your students have a more solid grasp on the scoping of Processing.py functions, you can always give the dictionary value at the start of the program!_

The nicest thing about having our values stored in a key:value pair within an object is that we can change these values easily, as we would with a variable. If we wanted to reassign the value to our key, it would look something like this:

```python
theLine["weight"] = 10 #this would assign the value of 10 to the "weight" key
```

We could use this to make something interesting happen in our program, such as with a conditional:

```python
if mouseX > 200:
    theLine["weight"] = 10
else:
    theLine["weight"] = 5
```

### Student Practice && Play (10 - 15 minutes)

After all that learning, students need some time to practice and play. Allow them time to create their own drawing tool or tools that will draw in an interesting way as the mouse moves.

Make your program unique - you can draw with a line, a shape, a design. You can adjust the fill and transparency, and even try to calculate values to change how your program looks. You can integrate conditionals to make it draw differently in different places. **You MUST use a dictionary to hold all of the changing values of your drawing tool!** Ask that students make the most UNIQUE program possible, as we will be looking at each other’s code!

For bonus points: think about how you can abstract your drawing tool (or tools) into functions so you can easily reuse them in other programs!

Encourage students to be creative. This is a great opportunity to experiment with code. They can use `mouseX` and/or `mouseY` for different values and test the output. They can play with the dist() function and experiment with color and shapes.

* Draw with different shapes.&#x20;
* Change the fill or stroke based on your mouse position (_remember to save values in an object literal!)_&#x20;
* Change the size based on your mouse position. (_remember to save values in an object literal!)_&#x20;
* Use the `random()` `dist()` function to vary your tool based on how fast your mouse is moving

### Wrap-Up (5 - 10 min)

Wrap-Up will be a bit longer to give students a chance to see each other’s work. A recommended strategy is this:

Ask students to pull up their program and hit play, so it’s running. Put on a song and allow students to circulate around the room - when the song stops, students must sit at the closest computer to them and explore the program and code. (Think: musical chairs, but always the right number of chairs.) Repeat this several times.

When you have finished, come together for student shout outs. Show student code and go over interesting examples.

### Extensions

Students can push the drawing program as far as they would like - either with their own imagination or trying one of the following:

* Explore the `dist()` function which will calculate the distance between two points - it's a great way to vary especially lines by calculating distance between where the mouse was (`pmouseX/pmouseY`) and where it currently is (`mouseX`/`mouseY`)
* **T**ry to code a rainbow by separating multiple colored lines and drawing with each one.
* Make the drawing tool different depending on where on the canvas you're drawing. Split the canvas into four; the drawing app should be different in each quadrant.
