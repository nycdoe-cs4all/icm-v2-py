---
description: How can I create my own variables to hold values in Python
---

# ✨ U1LA3.2: Creating Custom Variables

### Teacher Notes and Overview

**NB:** _This lesson technically covers NYS Standard **7-8.CT.7**_ _Design or remix a program that uses a variable to maintain the current value of a key piece of information. However, we know not all schools can guarantee a middle school sequence prior to this course. This lesson can be significantly abbreviated or skipped entirely based on the knowledge your students come in with!_

In this lesson, students will be introduced to the idea of creating their own variables to represent repeated values, or values that they may want to change without having to dig into their code.&#x20;

This lesson has two key phases: the first, in which students learn to create and code with their custom variables. In the second, students consider how variables can hold changing values in a DeltaMath activity. The DeltaMath activity is strongly encouraged if your students will take AP Computer Science Principles after this course, as these are AP prep questions. If that is not in the cards for your students, or if your students come in with a strong understanding of variables, that portion of the lesson can be skipped.

If you’ve never used DeltaMath, it is amazing and free and students can add as many teachers as they’d like. Make sure you have your teacher code handy! Pre-DeltaMath you might want to run through a problem together - it’s easiest if you write down values as you go. Additionally, keep the conversions of javascript to pseudocode posted either on chart paper or on a slide while students work.

_**NB:** Although data types are very important in Python, we have elected to save the deeper conversation about them until later in the curriculum in the interest of getting students started making their creations (and because they will primarily be using ints for the foreseeable future). If you disagree, please feel free to rearrange accordingly!_

### Objectives

**Students will be able to:**

* Identify repeated values in their code and use variables in their place.
* Create and implement custom variables.

### Suggested Duration

2 periods (45 minutes each)

A solid period is devoted to variable practice using DeltaMath. This is **strongly** recommended for classrooms using this as an AP Computer Science Principles prep course (or classrooms where variable understanding is weak), but it can be skipped if your students already have a thorough understanding of variables in computer science. Without this addition, this lesson could easily be one period

### NYS Standards

**7-8.CT.7** Design or remix a program that uses a variable to maintain the current value of a key piece of information.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

**Scope** - where a variable can be ‘seen’ by the computer within a program

**Global Variables** - variables declared outside of a function which can be used in any function.

**Local (script) Variables** - variables declared within a function whose scope is limited to that function

### Planning Notes and Materials

|                                                                                        Planning Notes                                                                                       |                                                                  Materials                                                                  |
| :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------: |
| DeltaMath is WONDERFUL, but make sure you’ve made your teacher account, classes, and assignment before class has started. You’ll need to distribute your teacher code for students to join. | While no materials are required, it may be beneficial to have a smart board/white board/chart paper available for tracking variable values. |

### Resources

* Do Now Starter Code ([Trinket](https://trinket.io/python/21a660caa2))
* NEED VIDEO TUTORIAL
* NEED LINK TO VARIABLE EXAMPLES

### Assessments

**Formative:**

**Summative:**

### Do Now/Warm Up (\~3 - 5 min)

Ask students to get computers and duplicate the Do Now Starter Code ([Trinket](https://trinket.io/python/21a660caa2)). Ask them to move all of the ellipses down thirty pixels. Once students start to finish getting all ellipses shifted down, ask them to move the ellipses back up 40 units. Then ask them to move everything to the right 20 units.

Once students are done, ask them what is frustrating about this process, and what might make it easier.

Students should be able to verbalize that changing every single number individually is frustrating. While most won’t be able to say that making a variable would make this a simpler process, they should be thinking that there must be someway for them to move everything together/at the same time. This is the launch to your activity!

### Position Elements with Custom Variables (\~10 - 15 min)

Instead of changing values manually, explain that we can use variables instead. A variable is just a “container” that holds a value which we can then apply and quickly change values in multiple places in our code.

Remind students that there are three steps to creating a variable:

**Declare** **& Initialize**- Declaring our variable is basically just telling the program “hey! I’m creating a variable, and this is what it’s going to be called.” And initializing that variable involves giving it a value. In Python, this takes place in one step, that would look like `myVariable = "value"` or `myVariable = 50`

**Use the variable** - Your code won’t break if you don’t use the variable, but then what was the point? If we add an ellipse at `ellipse(100, 100, myVariable , myVariable)`, our ellipse will be 50px wide and 50px high.

For Python, this will most often look like:

<figure><img src="../.gitbook/assets/Screen Shot 2022-11-04 at 1.32.21 PM.png" alt=""><figcaption><p>Image shows a variable being declared, initalized, and used in a Processing.py program.</p></figcaption></figure>

Notice where we placed our lines of code - the variable is way up at the top, before the `setup` function. This is done purposefully to create what we call a _global_ variable. This variable can be seen and used in any of our p5 functions.

If we create a variable inside of setup or draw, it will have a _local_ scope to that function. While this can be useful, and students will see this happen in future programs, it's not incredibly important at this moment or for things they will be immediately building. For this reason, we have prioritized their ability to get started over digging into code rules, best practices, and efficiency which will all build over the course of the curriculum. Please modify if you believe differently!

Once students have the idea of using variables, it's time to code one into the program. Begin by telling students you are going to make a variable that will control the y position because we can see that all the ellipses in our design have the _same_ y position. When code repeats, it is usually an indicator that we can make it more efficient.

```
from processing import *

circleY = 60
```

Next, utilize the y variable by plugging it into the code itself:

```
def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    ellipse(120, circleY, 60, 60)
    ellipse(200, circleY, 60, 60)
    ellipse(280, circleY, 60, 60)
    ellipse(360, circleY, 60, 60)
    ellipse(440, circleY, 60, 60)


draw = draw
run()
```



**As you code, discuss the following:**

* Why are we calling our variable `circleY`? Make sure students understand that we name variables useful things so we keep track of them - you might ask them how we could make this even more precise, and then change the variable name to something like ellipseY. You should also model adding comments with your variables about what this will control.
* Where could we use this variable? Students should tell you in the y position.
* What value should this variable have to start? If students aren’t sure, suggest starting at 60 to make sure it runs - then you can change it from there.
* Why do you think we named our variable above all the other functions? This is your introduction to global variables. Some students will see the visual cue that the variable is declared before we use it and that it’s used in two functions - some will not. It’s okay to explain this a bit more, they will see it again in more detail when they learn about random().

After the variable is added in, give it a few different values, running the program each time to see the change (you might want to make the canvas longer for this).
