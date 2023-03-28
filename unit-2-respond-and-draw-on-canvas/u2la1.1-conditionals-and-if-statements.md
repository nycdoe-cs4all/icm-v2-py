---
description: How can we add conditional statements to make our programs more interactive?
---

# ✨ U2LA1.1: Conditionals and If Statements

### Teacher Notes and Overview

**NB:** _This lesson technically covers NYS Standard **7-8.CT.8**_ _Develop or remix a program that effectively combines one or more control structures for creative expression or to solve a problem. However, we know not all schools can guarantee a middle school sequence prior to this course. This lesson can be significantly abbreviated or skipped entirely based on the knowledge your students come in with!_

This learning activity introduces booleans and conditional statements. Before students begin making conditionals to control visual parts of the canvas, they take a moment to think about the logic of coding off-canvas. Students will then create an interactive sketch that includes a visual element that changes based on a condition.

This is one of the first lessons that takes a trip off the canvas for students to practice Python syntax and logic. While it may be frustrating or seem dull to not be making creative coding pieces, it is useful for long-term student understanding for them to have the practice without the stress of getting everything to look just right. If you are teaching this curriculum to students with significant coding experience, please feel free to skip or speed up these sections as needed.

At this point, students have seen mouseX and mouseY and should understand that they hold a changing value. Students may wonder why conditions are important tell them that now it is time to make our sketches interactive and “intelligent” by adding a decision-making condition.

### Objectives

Students should be able to:

* Use an if-then statement&#x20;
* Create conditional statements (event handlers)

### Suggested Duration

\~2-3 periods (90 - 135 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.8** Develop a program that effectively uses control structures in order to create a computer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

**Conditional statements** - is a set of rules performed if a certain condition is met&#x20;

**Boolean expressions** - is a logical statement that is either TRUE or FALSE

**Prereq Vocab:**

1. Expression - is a group of terms (the terms are separated by + or − signs)&#x20;
2. Relational operators - < , > , >=, <=, && (and), || (or)

### Planning Notes and Materials

|                                                                                                                   Planning Notes                                                                                                                   |                                                           Materials                                                          |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------: |
| <p>Some of the examples might be too much for some students to copy so have some way students can have direct access to your project links. </p><p></p><p>You can assign the video tutorial (“Conditional Statements”) as homework or prework.</p> | <p>Pens/Pencils</p><p></p><p>Worksheet, printed or digital</p><p></p><p>Index Cards/Half Sheets for Exit Slip (optional)</p> |

### Resources

* NEED VIDEO ON CONDITIONALS IN PYTHON
* [Pseudocode Conditionals Worksheet](https://docs.google.com/document/d/17LyXObvxcdjTDSCO8O5r3nWQV2TXEFS3lEg\_xMRtiPs/copy)
* [Pseudocode Conditionals](https://youtu.be/1CJaGL9dQBA) (Youtube Video)&#x20;
* Conditionals Off Canvas Starter Code ([Trinket](https://trinket.io/python/19a09d8f12))

### Assessments

**Formative:**

* Use of conditionals during activity
* End of Lesson Wrap Up

**Summative:**

* Traffic Light (Upcoming Mini Project)
* Draw App (Upcoming Unit Final)

### Do Now/Warm Up (7 - 12 minutes)

Distribute the [Pseudocode Conditionals Worksheet. ](https://docs.google.com/document/d/17LyXObvxcdjTDSCO8O5r3nWQV2TXEFS3lEg\_xMRtiPs/copy)Ask students to fill out just the first column, and if necessary, offer suggestions for the first example to get them started. The rest they should be able to complete on their own. Ask them to, for now, ignore the second column.

After students have had time (\~3-5 minutes) to work on the first column, ask for some student shares, and then explain how you complete the second column by putting the plain English conditionals they’ve written into pseudocode.

Give students another \~5 minutes to complete the second column after you’ve given an example, and then review briefly before using this to launch into the coding portion of the lesson. For example:

|                    Action                    |                                         If/Else Statement                                        |                                                Pseudocode                                               |
| :------------------------------------------: | :----------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------: |
| **ACTION**: Go to the park with your friends | If (the weather is nice), then (I go to the park with my friends), else (I watch netflix inside) | <p>if theWeatherIsNice:<br>I go to the park with my friends<br><br>else:<br>I watch Netflix inside.</p> |

Give students another \~5 minutes to complete the second column after you’ve given an example, and then review briefly before using this to launch into the coding portion of the lesson.

It is important that students understand that an expression will evaluate to true or false. Then the computer will perform an action based on the given condition. Some students may ask where the words true and false words actually appear but tell them that the words are actually activation signals that the computer can only see - much like a light's on/off switch, we only see the word if we choose to print it, which we can do in some examples!

We want the computer to look at an expression and evaluate whether it is true or false, if it's true do one thing, and if it's false do another. Let's take a look at some expressions and evaluate them as true or false.

* 26>5 → 26 is greater than 5. Let's read that as a question. Is 26 greater than 5? Yes it is. This expression evaluates to "true."
  * If we wanted to test this in our editor, we could enter `print(26>5)` at the top of our program. Hit play, and we should see 'true' in the console!
* 10=14 → Since 10 is not equal to 14. This expression evaluates to "false"&#x20;
  * Try entering `print(10==14)` in a program. You should get 'false' in the console!
* 4>210 → This expression is also "false"&#x20;
  * Try entering `print(4>210)` in a program. You should get 'false' in the console!
* 2=2 → "true"
  * Try entering `print(2==2)` in a program. You should get 'true' in the console!

These "greater than" or "less than" signs are relational operators - they compare two numbers, which is what we're going to do in our first conditional statement.

In our conditionals, the boolean expression comes immediately after the 'if.'  If the expression evaluates to try, then hte computer will execute the code after the colon that is indented under the conditional statement. If it evaluates to false, the code is not runa nd the program will continue with the code that follows the expression.

```python
if 5<6:
    background(0) #background will turn black since 5 IS less than 6

if 5<4:
    background(0) #background will NOT turn black since 5 is NOT less than 4
```

Much like when writing functions, the indentations - or _white space_ - is very important in Python. Anything contained in a conditional needs to be indented underneath the conditional to be considered part of it!

### Conditionals Off Canvas (20 - 30 minutes)

Share students on the Conditionals Off Canvas Starter Code ([Trinket](https://trinket.io/python/19a09d8f12)) and direct them to make a copy that they can save.

Explain that this starter code wil lnot use the canvas and will run entirely behind the scenes, in the console. There are already some variables created with values as well as prompts for what students will be doing. Complete the noted code along with students to create code that will say 'I love your music!' if `theName` says Beyonce. For all other names, make it say 'Nice to meet you!'. The finished result should look like this:

```python
if theName == "Beyonce":
    print("I love your music!")
else:
    print("Nice to meet you!")
```

Again, note that the if and else are in line with each other, while the code that runs as a result of each is indented underneath them.

After, review with students the meaning of the == and that there are other comparative operators they can be using. Additionally, ensure they are aware that while we put strings - what they are currently seeing as words - in quotes, we do not for numbers.

* \== the same as&#x20;
* != not the same as
* **<** greater than&#x20;
* <= greater than or equal to&#x20;
* < less than&#x20;
* <= less than or equal to

Then, ask students to complete the remaining prompts while you circulate and assist. If you’d like, this could be an opportunity for pair programming or other collaboration.

Consider collecting this activity from students at the end so you can review before their second day of this content.

### Second Half OR Day Two Launch (5 - 10 min)

Based on student work from the previous day, display code that contains a common mistake (or mistakes) on the board. It may be helpful to also say ‘This code has # of mistakes… can you identify them?’

Ask students to identify AND determine fixes for the mistakes before you continue on.

**NB:** _We do not provide this as it should be based on specific issues you saw with your student's work!_

### Conditionals on Canvas Lesson (\~30 minutes)

Review the common mistakes with students and address any misconceptions. Students may need repetition from the first day about boolean expressions, what it means to be true/false, and the fact that you will not always be told 'true' or 'false' - you'll just be getting the coded results! Return to the light switch example as needed.

Bring students back for the code along. In a new project, create a shape on the screen with a variable to hold its color - remind students how to declare, initialize, and use a variable, and then how to change the color variable in a conditional. Create a change so that when the mouse is on one side of the screen, the color changes, and then changes back to the original. Use console.log(mouseX) so that students can see how the condition in the if statement is satisfied. Move the mouse back and forth a few times so that the shape changes color when mouseX increases and decreases: our sketch is now interactive and responsive to the user moving the mouse! At the end of the code along, you should have created something to the effect of:

```python
from processing import *

#VARIABLES
circColor = None

def setup():
    size(400,400)
    #GLOBAL VARIABLES USED IN SETUP
    global circColor
    circColor = color(255, 255, 0)

def draw():
    #GLOBAL VARIABLES USED IN DRAW
    global circColor
    
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)

    fill(circColor)
    ellipse(200,200,100,100)
    
    if mouseX > 200:
        circColor = color(255, 0, 255)
    
    else:
        circColor = color(255, 255, 0)
    

draw = draw
run()
```

**NOTE**: This builds on what students have been learning about using variables and their scope in Python. At the top of our code, we create a global variable called `circColor` that we intend to use in all of our functions. When we give it a starting value in setup, we need to remind the program that we are using this global variable in the `setup` function first.

Likewise, when we move to draw, we need to remind the `draw` function that it knows about `circColor` and that we intend to make changes. _**These global declarations only happen once per function/until the scope changes, which is why we are not saying it throughout our conditional statement.**_

A best practice is to have labeled, commented areas for these declrations to happen!

Once the code along is completed, ask students to do the following:

* Create a rectangle that will change height based on if the mouse is on the top or bottom of the screen
* Create a variable to hold the size of the circle. Change the size of the circle only if mouseX is at exactly 200, otherwise keep it the same.
* Create a variable to hold the color of the rectangle. Change the color of the rectangle only if mouseY is at exactly 200, otherwise keep it the same.
* Create a conditional that will change the color of the background when a specific condition is met. (You'll need a variable for background color!)
* Create a conditional that will make a new shape appear only when the mouse is in a certain position. No variables needed for this, as you'll be calling a shape function directly in your conditional statement.

As you code along through the other conditional examples ensure that students are:

* Commenting on their code. (Model examples for students as needed)&#x20;
* Using variables in the correct scope.&#x20;
* Using console.log() to debug and test&#x20;
* Saving their sketches with appropriate and clear titles.

Once they are done, ask students what else they could change about this shape or other things in the sketch, such as the background. Have them create variables and use them to change values of the shape itself when the mouse is in different positions, or create different shapes and variables to change with conditionals.

### Wrap-Up (10 minutes)

Students can submit code via a Google Form or submitting the link through a Google Doc if you would like to collect it. If not, have students come back together for a discussion on what struggles they encountered in this activity.&#x20;

Students can also lead code-alongs or walk through their code with the class.

**Guiding Questions**

* What is a boolean statement?&#x20;
* What are the two responses I can get from a boolean statement?&#x20;
* What is a conditional statement and how can I use it in programming?&#x20;
* What was challenging about creating an interactive sketch with boolean and conditional statements? Why? How did you solve the challenge? What was easy?

### Extensions

Adapt a previous sketch to add interactivity to it.
