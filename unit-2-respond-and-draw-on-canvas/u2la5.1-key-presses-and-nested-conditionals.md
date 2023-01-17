---
description: How can I use key presses to control elements of my program?
---

# U2LA5.1: Key Presses and Nested Conditionals

### Teacher Notes and Overview

In this learning activity, students learn to incorporate keyboard interactions into their sketches, responding to key presses and drawing letters on the canvas. Students learn to wrap conditionals so that they can create many color options with key presses.

This is a great chance to challenge student creativity and have them consider what they can control in a program. Push that as far as you can!

A common misconception is that students will call keyIsPressed in multiple if statements; this will sometimes make their program messy. A better solution is to have one ‘parent’ conditional that checks for any key being pressed, with every subsequent specific key condition nested inside of it.

This pair programming experience is very open-ended - try to encourage students to talk together about features for their program, rather than each person deciding for the group when it is their turn to navigate.

Push students to think about the user experience in leaving their feedback: did they know which keys to press without reading the code? How could this be improved?

### Objectives

Students will be able to:

Integrate key presses to control aspects of their program

### Suggested Duration

1 Period (\~45 Minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.8** Develop a program that effectively uses control structures in order to create a computer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **Key press** - p5 can register the most recently pressed key and whether a key is currently pressed&#x20;
* **Event Handlers** - alter the normal flow of a program when an action such as a key press or mouse movement takes place.&#x20;
* **`keyPressed`** - The system variable `keyPressed` is true if a key is pressed and is false if not

### Planning Notes and Materials

|                                                                                                       Planning Notes                                                                                                       |              Materials              |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------: |
| This lesson is fairly straightforward programmatically but is an excellent time to challenge your students to think about user experience, especially when dealing with key presses (which are not visible like a button). | No materials other than a computer! |

### Resources

* NEED KEYPRESS IN PYTHON VIDEO
* Starter Code ([Trinket](https://trinket.io/python/6be922cafa))
* Keycode Info ([From Reference](https://py.processing.org/reference/keyCode.html))

### Assessments

**Formative:**

* Do Now responses
* Learning Activity solutions
* Wrap Up responses

**Summative:**

* Interactive Drawing App (Upcoming Unit Final)

### Do Now/Warm Up (3-5 minutes)

Ask students to draw an ellipse in the center of their screen with a size of 50. Then, they should leave comments for as many aspects of this ellipse as possible that they may want to change.

### Press a Specific Key (10 - 20 minutes)

Ask students to share out some things they may want to change - remind them that this list could be long, and making buttons for everything might not make sense. Some things can change with a key press.

_For this section, you may have students start from scratch or utilize **this starter code**_ ([Trinket](https://trinket.io/python/6be922cafa))_, working from just one circle and saving the others for practice._&#x20;

Code along with students; suggest that you all change the size of the circle together. Take notes in code that you want the circle to get bigger when you press b and smaller when you press s. Be sure to demonstrate that because size will change, it needs a new variable to control it. **Explain that you will be changing many different attributes of this circle eventually, so even though you are just changing one thing for now, you are going to set up your code using an object, like so:**

```
from processing import *
from collide2d import *

circ1 = {}

def setup():
    size(400,600)
    global circ1
    circ1 = {
      "size":200
    }

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    ellipse(200, 200, circ1["size"], circ1["size"])
    
    
draw = draw
run()
```

After the variable and base code has been set up, demonstrate using `keyPressed` in an if statement but do not specify a key yet. Ask students to press b - the circle should get larger. Then ask them to press s or any other key and ask what the problem is:

```
if keyPressed:
    circ1["size"] += 5 #alternately, circ1["size"] = circ1["size"] + 5
```

Students should notice that all keys currently cause the circle to grow. This is your cue to begin discussing nested if statements, specifically ones that will check if the key is the same as a specific letter. With your students, set up “b” and “s” and then ask them to play again and determine what is wrong.

```
if keyPressed:
    if key == 'b':
        circ1["size"] += 5 #alternately, circ1["size"] = circ1["size"] + 5
    if key = 's':
        circ1["size"] -= 5 #alternately, circ1["size"] = circ1["size"] - 5
```

Students should notice that after a point, the circle gets too small and the key values ‘swap.’ This is because numbers have become negative and the computer is trying to react. Still, with the whole group, demonstrate how you could use && operators to safeguard against the circle getting too small or too large.

```
if keyPressed:
    if key == 'b' and circ1["size"] < width:
        circ1["size"] += 5 #alternately, circ1["size"] = circ1["size"] + 5
    if key = 's' and circ1["size"] > 0:
        circ1["size"] -= 5 #alternately, circ1["size"] = circ1["size"] - 5
```

### Pracitce and Play (10 - 15 minutes)

From there, send students to pair program. With their partners, they should decide on six additional features & keys to add to the program that will change the circle or any other element they’d like to add, swapping off driver and navigator as they add each one.

If using the starter code, they can start with the suggested changes on the different circles, but should add more beyond the 'task' challenges!

**🤓 OPTIONAL BUT ENCOURAGED**: Much like with `mousePressed`/`mousePressed()`, there is a `keyPressed` major callback function that students may choose to explore along with other keyboard based events in the Processing.py reference sheet. Depending on your students’ comfort levels, you may choose to review this with them, leave it as a general statement, or ignore it entirel

### 🤓 keyCode (Extra)

Students may want to use keys outside of letters, which is possible but works a bit differently. Some keys are 'coded' - the [reference sheet](https://py.processing.org/reference/keyCode.html) will explain how to check - and others require students to use the appropriate keyCode. Some keyCodes in Python can be found [here](https://anzeljg.github.io/rin2/book2/2405/docs/tkinter/key-names.html).

Coded keys will use a variable as their keycode, such as `UP` and `DOWN`, which are both commonly used in student projects.

For more information on where key codes come from, students can look into the Unicode system, which will be useful in AP CSP. [https://en.wikipedia.org/wiki/Unicode](https://en.wikipedia.org/wiki/Unicode)

### Wrap-Up (5 - 7 minutes)

Ask students to post their project links in a forum such as Slack or the Google Classroom. Then, have them view and comment on two other projects, leaving a glow and grow for each

**Guiding questions:**

* How does wrapping conditionals help our drawing app?&#x20;
* Which function would you use to change the size of the text?&#x20;
* What was challenging about wrapping one conditional inside another?

### Extensions

Give students specific and logically challenging tasks for their key presses, such as:

* Make your circle change color, but only to shades of yellow.&#x20;
* Make the stroke change color but never be the same as the circle color.&#x20;
* Make the strokeWidth change, but ensure that it will never be the same thickness as the circleSize.

