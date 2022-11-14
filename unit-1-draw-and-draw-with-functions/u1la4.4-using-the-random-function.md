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

If we hit play, we should get a random number in the console.
