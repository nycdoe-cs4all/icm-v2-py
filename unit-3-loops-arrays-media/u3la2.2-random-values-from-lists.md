---
description: How can lists help us simplify code?
---

# U3LA2.2: Random Values from Lists

### Teacher Notes and Overview

In this lesson, students will continue to practice creating and reading lists by randomly choosing elements from a list. This lesson is very brief and serves as a soft launch into the next mini project, which is essentially a longer, more creative student practice for this lesson. While they are separated here for readability, please plan to combine them during your instruction!

Selecting a random element from a list is an important concept to know when working on this unit's final project. It would be a good idea for students to share out their solutions to the exercises so that you can clear up any misconceptions.

**Nota Bene:**&#x20;

_Python has its own random module that can be imported separate of Processing.py, and Processing.py has a built-in, simplified random() function. The main portion of this lesson works off the assumption students are just working within the parameters of Processing.py, however, optional instructions for using `import random` and the random module are included. These instructions should be considered an extension - proceed only if your class is ready for something extra, or if you prefer working with that module over the methods in Processing.py._

### Objectives

Students will be able to:

* Explain how the random() function serves to return a random number&#x20;
* Explain how the floor() function returns the input, rounded down&#x20;
* Use the combination of random() and floor() to select random elements from arrays

### Suggested Duration

45 minutes (\~1 class period)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.7** Design or remix a program that utilizes a data structure to maintain changes to related pieces of data.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* List - an ordered series of data&#x20;
* Index - a position within a list
* Element - a piece of data in a list
* **Zero-Indexed** - The first element of a list has an index of 0, not 1&#x20;
* **`random()`**` ``` - a function that will return a random number in between its two parameters
* **`int()` ** - converts a float into an integer by rounding down to the closest integer value
  * _You could also use `round()` which will round up or down._
* **`len()`** - returns the length of a list as a numeric value

### Planning Notes and Materials

|                                                     Planning Notes                                                    |           Materials          |
| :-------------------------------------------------------------------------------------------------------------------: | :--------------------------: |
| There are no specific planning notes for this lesson, but it is the first lesson students will be using media - whoo! | No special materials needed. |

### Resources

* NEED RANDOM/LIST PYTHON VIDEO
* ``[`random()` in Processing.Py](https://py.processing.org/reference/random.html) (Reference Sheet)
* [Python List Methods](http://localhost:5000/s/oF62wG4MMbP5xRgX3R88/) (W3 Schools)
* **Optional:** [**`random.choice()`**](https://pynative.com/python-random-choice/) **** (Extension)

### Assessments

**Formative:**

* Do Now - ability to pull from an array
* Learning Activity - use of `random()` and `floor()`

**Summative:**

* Create a Fortune Teller

### Do Now/Warm Up (5 -8 minutes)

Open a blank editor and using whatever color-choosing application you like, create a list of at least 10 different colors. (If you have time, continue adding colors.)

_Students should use their work from the previous lesson as reference - as they begin this warm-up activity, circulate to ensure that you can help them troubleshoot any errors as they get used to both arrays and storing this particular data type in lists._

### Using `random()` with lists (\~8 - 15 minutes)

Explain to students that today, they are going to build a program with shapes that change color randomly whenever the program is run. This should feel familiar - they've done it before - but they've never done it by pulling random values from the array. And since that can be a little tricky, that will be the focus!

`random()` was introduced way back in Unit 1 (and likely used in Unit 2), so this should be familiar to students. If you think it's needed, feel free to take some time and review the following:

* `random()` is a different sort of function than something like `ellipse()` - like some of the ones we've written, it _returns_ a value instead of displaying something on the screen.
* It returns a random value based on a maximum (like random(100), which would be any number between 0-100) or a range (like random(5,50) which would be any number between 5-50).
* We can use this anywhere we would use a number, or even call it to stash our random value in a variable, as has been our best practice.
* The value will be randomized each time the `random()` function is called.

Ask students to put a shape somewhere on their canvas and explain we will be giving this shape a random fill from our array.

The first attempt might look something like this, and will certainly end in an error:

```python
from processing import *
from collide2d import *

randomColors = []
randomChoice = None

def setup():
    size(400,600)
    global randomColors, randomChoice
    randomColors = [color(255, 0, 0), color(0, 255, 0), color(0, 0, 255)]
    
    randomChoice = random(3) #this is the length of the list
  

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    fill(randomColors[randomChoice])
    ellipse(200, 200, 100, 100)
  
    

draw = draw
run()
```

So, why did this end in an error? Well, if we comment out the fill line and add this in the setup after line 10:

```python
print(randomChoice)
```

We should see that we are getting random numbers, but they are not random numbers that exist in our array. Things like 3.1415903 aren't values that are in our array - so we need to make sure that our program is rounding down to the nearest whole integer.

Why round down? Our list goes 0 - 2 even though there are 3 items - if we rounded up, we would need to make some adjustments later. Which is fine, just a choice that can be made!

Show students this adjustment that can be made to the code:

```python
from processing import *
from collide2d import *

randomColors = []
randomChoice = None

def setup():
    size(400,600)
    global randomColors, randomChoice
    randomColors = [color(255, 0, 0), color(0, 255, 0), color(0, 0, 255)]
    
    randomChoice = int(random(3)) #this is the length of the list
  

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    fill(randomColors[randomChoice])
    ellipse(200, 200, 100, 100)
  
    

draw = draw
run()
```

We should now not only see numbers being logged that are within our list, but we should also be able to get an ellipse with a random fill and no error messages. Hoorah!

There's just one more thing we need to fix before we go off to play with this idea. Notice how right now, we are taking saying `random(3)` because the array is 3 items long? That could become a problem later if I were to add colors but forget to update this piece of code. Or what if I was making a program where users could add their favorite colors and the program would draw with them? &#x20;

Right now, the 3 **** in our random function is what we call a **hardcoded value.** Things that are **hardcoded** will always be the same in a program - and there are plenty of things we would want to be hardcoded, such as the score of a game starting at 0, or the timer for a soccer match half starting at 45, for example. But in this instance, we want to make sure that the value in random is **dynamic** so that if we make changes to our ray, the rest of our program is taken care of.

Remember that **`len()`** function we learned about in the last lesson? This is where it can come into play, like so:

```python
randomChoice = int(random(len(randomColors)))
```

Essentially, this is what is happening in our code:

<figure><img src="../.gitbook/assets/Screen Shot 2023-02-06 at 11.19.34 AM.png" alt=""><figcaption><p>Breakdown of the order of operations in choosing a random value based on the length of an array.</p></figcaption></figure>

By changing the value to the length of the list, we will ensure that even if our lists gets longer (or shorter), the code will always work correctly. This kind of thinking is a best practice as we continue to make our programs more and more complicated. Always be asking yourself: what can I do to make sure this won't break in the future?

### Student Practice (10 - 20 minutes)

**NB:** _Allot as much or little time as you'd like for this - it could easily become a quick CFU before moving into the fortune teller mini project, which is a much more engaging practice, but not as repetitive as this suggested exercise._

Ask students to create a design where at least 5 shapes change randomly using colors from the list. _All_ shapes in their design should pull colors from the list, to practice calling array elements again, but they do not all need to be randomized.

### Wrap-Up (5 min)

Ask students to post their project links in a forum such as Slack or Google Classroom. Then, have them view and comment on two other projects, leaving a glow and grow for each

Guiding questions:

* How can we use the random function to select a random element in the list?&#x20;
* What would happen if we did not use the `int()` function?

### Extensions

There are several ways that students can push their understanding of arrays:

* Ask students to create a button that will 'reroll' the randomly chosen colors.
* Have students create a list to hold the random values they generate. They can explore using [.`append()`](https://www.w3schools.com/python/ref\_list\_append.asp) to add values to a list, and then call the values of that list for each shape. (This won't be as neat as it could be, yet, since they have not yet explored for loops and list.)
* Which goes to say - could they create a for loop to work through some of the list stuff? Advanced exploration!
