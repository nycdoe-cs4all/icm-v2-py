---
description: How can I use randomness in my code?
---

# U1LA4.4: Using the Random Function

### Teacher Notes and Overview

This lesson's goals are three-fold: first, to get students used to the idea of randomness, which is a powerful programming tool. Second, to show students that you can hold random values in variables to use in your program, where they will often serve as arguments in your functions. Finally, students will work on reinforcing their function writing skills and will add the knowledge of how to create optional values for parameters.

**NB:** _There is_ [_random module_](https://www.w3schools.com/python/module\_random.asp) _that you can import to use in Python. We have chosen_ _for the purpose of this curriculum to use the random() function built into the p5 library to keep things simple. Students will be introduced to the idea of importing modules and functions later in the curriculum._

### Objectives

**Students will be able to:**

* Use `random()` to generate different positioning, sizing, colors
* Assign `random()` to a function
* Use`random()` in the correct scope

### Suggested Duration

1 Period (\~45 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.5** Modify a function or procedure in a program to perform its computation in a different way over the same inputs, while preserving the result of the overall program.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **Function call:** The name of a function, typed when you want to execute the specific steps the function represents&#x20;
* **Parameters:** The values of a function that can be controlled/altered whenever the function is called (inputs)&#x20;
* **Arguments:** Values passed through to a function’s parameters (input values)

### Planning Notes and Materials

|                                                                                                                                Planning Notes                                                                                                                                |                                                              Materials                                                             |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------: |
| <p>This lesson does not require much advanced-planning, but you should review the code they will be turning into functions.</p><p></p><p> If your students struggle conceptually with the idea of randomness, having manipulative examples (dice, cards) may be helpful.</p> | <p>Starter Code, Computers.<br><br>Optionally: Dice, cards, or other manipulatives that can be used to demonstrate randomness.</p> |

### Resources

* Do Now && Lesson Starter Code ([Trinket](https://trinket.io/python/5bb4793361))
* [Coding Train: Random Function](https://www.youtube.com/watch?v=POn4cZ0jL-o) (Youtube Video) NEED PYTHON VERSION

### Assessments

**Formative:**

* `weirdFace()` function definition
* `creepFace()` function definition
* Parameter and randomness challenges

**Summative:**

* Create an Emoji (Upcoming Mini Project)
* Abstract Album Art (Upcoming Final Project)

### Do Now/Warm Up (\~5 - 10 minutes)

Share students on the Do Now Starter Code ([Trinket](https://trinket.io/python/5bb4793361)). Ask them to duplicate and then create both a `creepFace()` and `weirdFace()` function. Each should accept an argument to control the x position and y position of the entire emoji. Students should call their function to ensure it works!

**NB:** _You can ask every student to complete both as part of a longer do now, or choose to have them pair program. You could also have half the class complete one while half does the other, and then ask a student from each group to share so that they all have all the code before moving on._

### Using the `random()` function (\~10 minutes)

Students have, by now, seen the `random()` function used in certain places - but they likely have not used it yet. Explain to students that they are going to be learning how to use `random()` to make it so their sketches change each time they hit play. Before starting, explain that `random()` is a function, but unlike `ellipse()`, `rect()`, or other shape functions they're used to working with, this one doesn't make something appear on the canvas: it instead returns a random value that we can use in our program.

We can see how this works by adding a line of code to our `setup()` function:

```
from processing import *

def setup():
    size(400,400)
    print(random(5))
```

If we hit play, we should get a random number in the console. You'll notice this is a random value between 0 and 5, but it's a long decimal value! This is okay if we are using it somewhere that expects a decimal, but in Python, integers and decimals - which are called floats - are actually seen as totally different data types. If we wanted to make this code more useful, we could turn it into an integer by wrapping the random value in the `int()` function:

```
from processing import *

def setup():
    size(400,400)
    print(int(random(5)))
```

Much better!

**`random()` can be used in a few ways:**

* If you just type`random(num)`, it will assume you want it to choose from a range of 0 to the`num`you entered. It is _exclusive_ of the entered number, meaning if you put in 5, it will show every number up to but not including 5.
* If you type `random(5,20)`, it will give you a value anywhere between 5 and 20. It will be _inclusive_ of 5 - meaning that it could show that number - but _exclusive_ of 20, meaning it will show up to but not exactly 20.
* As mentioned, there is an entirely separate module in Python dedicated _just_ to random and generating different random thing. We aren't teaching that in this course since Processing.py has a `random()` function built-in, but it is perhaps worth knowing it exists for future projects!

Now, getting one number is great - but check out what happens if we put that same `pring(int(random(5)))` in the `draw()` function. Once we move the `print()` into draw, we should see that we get different values _constantly_ - this is because while `setup()` runs once at the start of the program, `draw()` is on a constant loop. It runs roughly 60 times per second, which means we get back a wide range of values!

This can be a good thing, but it can also cause strange results that sometimes look a little nauseating. Let's test this out by using random in one of our functions - in this case, we will use the plain ellipse that we didn't turn into a function. **Please note that this first example will cause a flashing design. It is necessary to warn any students who may have epilepsy or other sensitivities to not participate, or that you may want to skip this entirely if you suspect that could become an issue.**

Let's say we want our ellipse to change it's width between the values of 50 and 150. Our code might look like this:

```
ellipse(300, 300, random(50, 150), 100)
```

But when we hit play, it's flashing like crazy! Again, this could be a desired feature, but for many people this sort of design might make them feel a little uneasy to full-on queasy. So what if we want to pick a random value and not let that random value change until we hit play again?&#x20;

In that instance, we would want to give our variable the value in `setup` so it is chosen once at the start of the program and then never again until we run the program again. Our code would look something like this:

```
from processing import *

circW = None

def setup():
    size(400,400)
    global circW
    circW = random(50, 150)


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    ellipse(300, 300, circW, 100)


draw = draw
run()
```

It's very important that students understand that `random()` just chooses a number, so we can use the function - or the results of that function saved in a variable - anywhere we would a numeric value. Pause and **ask: **_**What else could we control with a random value?**_

### **`random()` in colors and colors in variables (\~7 - 10 min)**

One thing we may want to control for is color. Continue coding along with students to explain that as we've seen, just using `random()` in draw can lead to flashy crazy results - if we don't want that, we may need to create variables that hold either values to make up our color, or the color as a whole. Maybe we only wanted one or two amongst the red/blue/green or hue/saturation/brightness values that make up a color to vary - we might do something like this:

```
from processing import *

blue = None
green = None

def setup():
    size(400,400)
    global blue, green
    blue = random(255) #any amount of blue possible
    green = random(75, 125) #green must stay between 75 and 124


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    stroke(200, green, blue)
    ellipse(300, 300, 100, 100)


draw = draw
run()
```

If we are choosing to vary our entire color, or to save any color to a variable, we need to make sure the computer knows we are using a color data type. That would look something like this:

```
from processing import *

randomColor = None

def setup():
    size(400,400)
    global randomColor
    randomColor = color(random(255), random(255), random(255))


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    stroke(randomColor)
    ellipse(300, 300, 100, 100)


draw = draw
run()
```

In this example, we are picking three random numbers and telling the computer that all three together make a color. When we plug in the `randomColor` variable, the computer sorts out the three numbers and processes them to create a color. We do not _have to_ use random to do this and can actually save any color this way! something like `magenta = color(255, 0, 255)` would save those same color values to the variable `magenta`.

### Using Random Values as Arguments (\~12-20 min)

You have one final moment in your code along, then the students are being set free! Explain to students that so far, they've done a great job of creating functions where we can  move the design around, but sometimes we may want to change things about the design, and that means we should be able to change the design _randomly_ as well.

What if we want the little eye on the `creepFace()` to be a different size, and allow whoever is calling the function to set that different size? We can adjust our function so that a parameter controls that size, and we can even set the parameter to have a default, optional value.

```
def creepFace(xPos, yPos, eyeSize):
  fill(255, 255, 0)
  stroke(0)
  strokeWeight(0)
  ellipse(xPos,yPos,100,100) #200, 200
  strokeWeight(1)
  ellipse(xPos-20, yPos, eyeSize, eyeSize)
  strokeWeight(5)
  ellipse(xPos+20, yPos, 20, 20)
  strokeWeight(1)
  rect(xPos-20, yPos+20, 40, 4)
```

The above would allow us to enter a third value to control `eyeSize`. If we are nervous people may forget, or they may want to preserve the original design, we can give `eyeSize` a default value like so:

```
def creepFace(xPos, yPos, eyeSize=10):
  fill(255, 255, 0)
  stroke(0)
  strokeWeight(0)
  ellipse(xPos,yPos,100,100) #200, 200
  strokeWeight(1)
  ellipse(xPos-20, yPos, eyeSize, eyeSize)
  strokeWeight(5)
  ellipse(xPos+20, yPos, 20, 20)
  strokeWeight(1)
  rect(xPos-20, yPos+20, 40, 4)
```

Now, if nothing is entered, the function will still work with the default size. Anything entered in the third position will override this, however. We can test this by drawing a few more creepFaces and using some variables to help us out:

```
from processing import *

randEye = None

def setup():
    size(400,400)
    global randEye
    randEye = random(5, 25)

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    stroke(randomColor)
    ellipse(300, 300, 100, 100)
    
    #Creep Face
    creepFace(200, 200) #will have default value for eye
    creepFace(100, 200, randEye) #will have varying eyeSize


draw = draw
run()
```

This can be a weird idea for students, as we are using a variable to plug into a place where a parameter is already defined by a kind-of variable placeholder. Remind students that they do this _anytime they use variables_ because people have written function definitions for all the shapes they use - they just don't normally see the definition the way they do when drawing it themselves!

From here, ask students to complete a few mini-challenges of adding parameters to their function and using variables with random values to control them.

* In `creepFace()`, create a parameter to control the `strokeWeight` of the bigger eye. Be sure to give it a default value.
* In `creepFace()`, create a parameter to control the width of the mouth Be sure to give it a default value.
* In `creepFace()`, create a parameter to control the y position (how far up/down it is) of the mouth. Be sure to give it an optional value.
* In `weirdFace()`, create a parameter to control the color of the fill.
* In `weirdFace()`, create a parameter to control the color of the stroke.

### Wrap-Up (\~3-5 minutes)

Display several examples of student work with successes in changing colors and sizes. Make sure that you show what's happening in their code and discuss with a class to make sure everyone is on the same page and give space to answer any questions or address any conceptual misunderstandings!

If your class struggled, base your discussion around problems they encountered rather than a tutorial. If they are close to finding a solution and you have extra time, you can walk them through in a code-along, but do not anticipate or force getting to that place.

**Student Assessment Guiding Questions:**

* Why does the random() function behave differently when used in setup vs. draw? How could this be a benefit, and how could it create problems?
* What is the benefit of using a default value in a function?
* How can we use the random function to create games in the future?

### Extensions

As this lesson is mostly a code-along, it is unlikely that students will race ahead of where the class is. If students are in a place to move forward, have them start trying to create their own designs, or utilize past designs such as their robot, that they can shift using variables for x and y while preserving the design itself. Creating designs that use triangles, quads, or shapes of their own creation are also useful and challenging.
