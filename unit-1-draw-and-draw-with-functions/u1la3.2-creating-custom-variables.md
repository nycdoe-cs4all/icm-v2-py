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

The one difference comes up if we want to use a Processing.py function when giving our variable. Students will not see this quite yet, but it's worth naming - things like the `random()` function cannot be used outside of `setup()` or `draw()`. To get around this, we declare and initialize a variable with no value, and then give the it value in `setup()` to start the program. It would look something like this:

<figure><img src="../.gitbook/assets/Screen Shot 2022-11-14 at 3.21.24 PM.png" alt=""><figcaption></figcaption></figure>

Notice where we placed our lines of code - the variable is way up at the top, before the `setup` function. This is done purposefully to create what we call a _global_ variable. This variable can be seen and used in any of our p5 functions.

If we create a variable inside of setup or draw, it will have a _local_ scope to that function. If we want to change the value of a global variable, we need to use the `global variableName` like what is happening on line 7; that will ensure we change our global variable rather than making a new local one with the same name.

This is important, but will not come up for several more lessons. For this reason, we have prioritized their ability to get started over digging into code rules, best practices, and efficiency which will all build over the course of the curriculum. Please modify if you believe differently!

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

### Move a Value with One Variable (\~10 - 15 min)

Ask students: we’ve changed the y position, but now I want to move this entire design to the left or right by changing the x, as well. Why is that going to be different from changing the y position?

This should be a nice callback to using `mouseX`/`mouseY` to move triangles and quads in the previous lesson. Hopefully, students will recall that they need a variable and an 'anchor point' that they can base the other points around. As a best practice, consider copy/pasting the original code into a comment so you have reference for where you started and where you are going!

Similar to the previous lesson, we will need a starting point - in this instance, we will use the far left ellipse, but it is important to stress that does not always need to be the case. Using the initial points from the first ellipse, create your starting variables:

```
from processing import *

circleY = 60
circleX = 120
```

We will then replace these in our starting ellipse and continue from there, thinking about how far away each of the other ellipses is from the original starting location. In the second ellipse, the X position is at 140, or +80 units away from our start. So we could code it like so:

```
def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    ellipse(circleX, circleY, 60, 60) #original 120, 60
    ellipse(circleX + 80, circleY, 60, 60)
    ellipse(280, circleY, 60, 60)
    ellipse(360, circleY, 60, 60)
    ellipse(440, circleY, 60, 60)


draw = draw
run()
```

Be sure to run the program; students should notice that nothing happened, but that’s a good thing because it means the positions stayed the same even while using a variable. If students have any misconceptions or errors, please feel free to indulge them and run the program to see the results before explaining what's happening.

Once all of the ellipses have been finished, your x values should look like this:

```
circleX
circleX+80
circleX+160
circleX+240
circleX+320
```

Once you're done, demonstrate how you can then adjust the variable value in just one place and maintain the exact design while moving it around the canvas.

### Move a Taijitu with Two Variables (\~10 - 15 min)

After the example, ask students to pair program with their taijitu symbol. (You can have one person duplicate their symbol, or share an exemplar to give everyone a fresh start.) Explain that their goal is to create a variable called `symbolX` and `symbolY` and remake the code so that they can change the value of just those variables and move the entire symbol around the page.

Each partner should be responsible for one variable that they will navigate for while the other drives, and then they will swap.

Time permitting, share student solutions on the board.

### DeltaMath Variable Practice (Optional, 30 - 45 min)

_Likely, this will be the beginning of a new period. You can use the question below as a 'Do Now' activity that launches into the lesson prior to practice. On the_ [_DeltaMath.com_](https://www.deltamath.com) _website, under Computer Science -> Pseudocode Exercises -> Setting Variable Values, there are problems that look like the following. You’ll want an assignment of 10-15 of them._

Determine what is printed by this code:

<figure><img src="../.gitbook/assets/image (1) (1) (2).png" alt=""><figcaption><p>Image shows a practice variable assignment question from DeltaMath.com</p></figcaption></figure>

_Sample problem solution: **4**   **5  5**_

DeltaMath uses the pseudocode seen on the AP exam, so it’s not written in any actual language, but it does follow the same logic of running from top to bottom. It’s fairly intuitive, but we don’t want it to confuse any students. Before setting your students free, be sure they are aware of the following:

| DeltaMath Pseudocode |   Python   |
| :------------------: | :--------: |
|      **b <-- 4**     |   `b = 4`  |
|    **DISPLAY(b)**    | `print(b)` |

If students get them wrong, encourage them to use the 'next' feature on DeltaMath to step through the code so they can understand their mistakes.

### Wrap-Up (\~5 minutes)

You may want to bring students together to discuss successes and sticking points from the variable practice. DeltaMath does a roll up of accuracy and completion for each student, so you will have access to their data if you want to give a formative assignment grade or something similar.

### Student Assessment Guiding Questions

* What is a variable? How do you use it in your code?
* What are the benefits of using variables?
* How did you use variables in your project and why that way?
* What was challenging when using variables?

### Extensions

As this lesson is mostly a code-along, it is unlikely that students will race ahead of where the class is. If students are in a place to move forward, have them start trying to create their own designs, or utilize past designs such as their robot, that they can shift using variables for x and y while preserving the design itself. Creating designs that use triangles, quads, or shapes of their own creation are also useful and challenging.

You might also have them start experimenting with using `mouseX` and `mouseY` to move their design around.
