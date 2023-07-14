---
description: How can I use mouse clicks in Processing.py?
---

# U2LA4.2: Mouse Clicks and Shapes as Buttons

### Teacher Notes and Overview

This lesson builds on using the collision functions to not only determine if the mouse is hitting a shape, but now to use built-in Processing.py variables and functions to determine if the mouse is being pressed. Make sure students have completed the prior lesson before beginning so they are up to speed on what is happening and have all the necessary resources.

Adding clicks to their previous work is not a huge lift, but it is impactful enough to feel mind-blowing to students.

Students may be confused as to why a variable is changing in conditionals instead of a fill or other action - the reason for this is efficiency in drawing order, and to make sure each button changes independently of the others. If students are struggling, try this quick unplugged example:

* Have two students stand at the front of the room as you walk through the code. When the variable is declared, hand one student a paper cup or plate with the variable name on it.&#x20;
* Make sure students understand that it is an empty holder until initialized. When the variable is initialized, put a marker (or another colored writing utensil) in/on the cup/plate.&#x20;
* &#x20;Swap back when the if statement is not activated.
* Give another color to the second student. When the fill is called using the variable, have the first student take the marker from the cup/plate and mime coloring.&#x20;
* When the if statement is activated, have the second student swap the marker from the first student’s hand.

Code reading is much more challenging than code writing. Encourage students to read and discuss code as often as possible!

### Objectives

Students will be able to:

* Use conditionals to define a reactive shape button
* Use mousePressed (the variable) and mousePressed() (the function) to create mouse click reactions

### Suggested Duration

1 Period, \~45 minutes

_Use your best judgment in timing! This lesson can easily be completed in one period, however, if you believe students need more practice, give them ideas of how they could keep honing these skills and allow them time to work!_

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.8** Develop a program that effectively uses control structures in order to create a computer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **mouseIsPressed** - this is a built-in variable that is True when the mouse button is pressed, and False when it is not pressed&#x20;
* **mousePressed()** - a major callback function in the p5 library that executes once, each time the mouse is pressed.
* **Nesting Conditionals** - When one conditional lives within another -- so both of the conditions have to be met before your code will execute.
* **Efficiency** - In this case, making it easier and faster to debug and edit your code&#x20;

### Planning Notes and Materials

|               Planning Notes               |                                                                    Materials                                                                   |
| :----------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------: |
| No specific planning notes for this lesson | If you need to act out changing values of variables in conditionals, having paper plates or cups on hand can help with variable understanding. |

### Resources

* NEED COLLIDE AND CLICK VIDEO FOR PYTHON
* Starter Code - Completed in Last Lesson ([Trinket](https://trinket.io/python/9eee468991))
* Blank Template w/ Collision Library ([Trinket](https://bit.ly/collidepy) | [Documentation](https://github.com/cmorgantywls/collidewithprocessingpy))

### Assessments

**Formative:**

* Program from learning activity with clickable buttons
* Wrap Up Response

**Summative:**

* Lightswitch Game (Upcoming Mini Project)
* Interactive Drawing App (Upcoming Unit Final)

### Do Now/Warm Up (3-5 minutes)

Ask students to open up the following website and just record what they notice about how they must interact with it:

{% embed url="https://bubblespop.netlify.app/" %}

### Making Shapes Clickable (10 - 20 minutes)

The brainstarter should have shown students that hovering isn't always enough: to engage with the bubble wrap, they need to be able to click on the shapes that are on the screen. In their Processing.py programs, there are several ways to do this, but all of them utilize what we call event Listeners - that is, something in the program that is waiting to see if an event, like a mouse being clicked, is happening.

To start, we are going to use the variable version: `mousePressed`. Please note that in Python, the variable and function are named the same (different from the p5.js version), and that can be _really confusing_. This is a great time to reinforce that variables are just the word, while functions will always have parentheses after!

The variable `mousePressed` holds a boolean variable, which either holds the value false if the mouse is not being pressed or true if the mouse is being pressed. This works great for certain situations and it’s pretty quick and easy to deal with. Later in the lesson, we will look at using the function for checking of the mouse is pressed and we will compare the pros/cons of each.

Have students open up their code from hovering on shapes in lesson U2LA4.1. With the students, show them how they can include this variable with the collision functions in order to make the line change color once it has been clicked. The code should look something like this:

```python
if collideLinePoint(25, 20, 155, 70, mouseX, mouseY, 0.3) and mousePressed:
    lineColor = color(255, 0, 255)
```

Now, this will change the line and keep it changed forever. If they ONLY wanted the change to happen while the mouse was being pressed, they could adjust their code:

```python
if collideLinePoint(25, 20, 155, 70, mouseX, mouseY, 0.3) and mousePressed:
    lineColor = color(255, 0, 255)
else:
    lineColor = color(0)
```

Once you’ve finished, ask students to go back into their code and try making all of the other shapes clickable, as well. This should not be a particularly long task; when they are done, regroup and ensure they understand that using `mousePressed` in any conditional will determine if the mouse is being clicked or not - it does not need to take place on a shape.

_If students need an extra challenge, they can code in elif statements or separate conditional statements for hover reactions different from the click reactions, or click reactions if you are 'close' but not on a shape._

### Problems Counting (10 - 20 minutes)

Now, `mousePressed` is a great quick solution to our problem of getting information from the mouse. However, it does have some limitations which we will see in this section. If you feel that your students are really struggling with the code or with big concepts, this may be something you choose to come back to at a later date/time or split into multiple lessons to allow time to process.

Explain to students that we will be trying to make a variable that counts, or keeps score - this is the backbone of a lot of games and it's a useful skill to have. Go ahead and start a new program with the collide library linked. Ask students to create a single ellipse in the middle - this is what you'll be clicking on! Then, declare a variable at the top of your program called `score` and give it a starting value of 0. You can either display it somewhere on the screen using the `text()` function, or you can choose to do this all in the console using `print()` - just decide in advance. Ask students to figure out how you could make this score increase by one each time the circle is clicked. Give students time to think and work (ideally in pairs or groups) before coming together to make sure agree on this:

```python
if collidePointCircle(mouseX, mouseY, 200, 200, 100) and mousePressed:
    score = score + 1 #alternately, score+=1
```

This will make the score increase, but students will probably be quick to notice something odd: despite the fact that they told it to increase by 1, it will increase in jumps. Explain that this is because `mousePressed` checks to see if the mouse is clicked in the moment the code is run - and because the draw function runs on a loop VERY QUICKLY, we are often not fast enough to lift up our finger before it loops and counts it a second, third, or even fourth time.

To help us when this problem arises, there are other tools built into the Processing.py library that interrupt the folow of the draw function and run only once when an action occurs. The one we will look at today is the `mousePressed()` function - but they can look on the Processing.py reference page under 'Input' if they'd like to explore more.

Students will need to see how to add this function and will likely need reminders about Python indentation. This happens _outside_ of the draw function - meaning it is aligned with the left side of the canvas - but before the run and draw lines. Code along with your students and explain the logic to get something like this, where the code will ONLY run when the mouse is pressed:

```python
from processing import *
from collide2d import *

score = 0

def setup():
    size(400,600)

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    ellipse(200, 200, 100, 100)

def mousePressed():
  global score
  if collidePointCircle(mouseX, mouseY, 200, 200, 100):
    score+=1
  print(score)
    
    
    

draw = draw
run()
```

Now, if we knew this was always a thing we wanted to do, we could also make a function that would update the score when clicked - ask your students to think through what this might look like, and try to build it out together if you're feeling ambitious! (It would need to take in the score and return the score, and you would then save that return value back to the score variable. So when called, it might look like: `score = updateScoreWithCircle(score)`)

From here, you may ask students to try to make other things clickable using mousePressed, or simply wrap up the lesson.

### Wrap-Up (\~5 minutes)

Ask students to respond to one or more of the following questions:

* What is the difference between the variable `mousePressed` and the callback function `mousePressed()`?&#x20;
* Why might you choose to use one instead of the other?&#x20;
* Which of the methods we learned today seems easier to you?&#x20;
* Describe a situation where `mousePressed` works fine.&#x20;
* Describe a different one where you would prefer `mousePressed()`.

### Extensions

Encourage students to further explore conditional logic by using nested if-else statements to set each shape so it is one color when a mouse is not touching it, another color when the mouse is hovering, and a third color when it is clicked.
