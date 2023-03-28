---
description: How can we write multiple conditions to our code?
---

# ✨ U2LA1.2: Conditionals and if, elif, and else statements

### Teacher Notes and Overview

**NB:** _This lesson technically covers NYS Standard **7-8.CT.8**_ _Develop or remix a program that effectively combines one or more control structures for creative expression or to solve a problem. However, we know not all schools can guarantee a middle school sequence prior to this course. This lesson can be significantly abbreviated or skipped entirely based on the knowledge your students come in with!_

This learning activity builds on the students’ knowledge of conditional statements. They will use conditional statements to create a sketch of a traffic light in future lessons that changes colors based on the mouse position, and this prepares them for that activity

Students should have a solid understanding of conditionals and how it is satisfied through a boolean. This lesson will focus heavily on creating more complex algorithms through the use of conditionals. Therefore it is important that students add comments to keep track of the sketches control flow. Students will also benefit greatly from peer programming because they can model their thinking behind their code.

### Objectives

Students will be able to:

* Use an if-then statement&#x20;
* Use else if and else statements&#x20;
* Create conditions statements (event handlers)&#x20;
* Elaborate on how to satisfy a condition.

### Suggested Duration

\~1-2 Periods (\~45-90 minutes)

### NYS Standards

_**7-8.CT.8** Develop or remix a program that reffectively combiens or or more control structures for creative expression or to solve a problem._

**9-12.CT.8** Develop a program that effectively uses control structures in order to create ac omputer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* Conditional statements - is a set of rules performed if a certain condition is met&#x20;
* Else - the second half of a conditional statement covers every outcome not specified in “if”&#x20;
* Boolean expressions - is a logical statement that is either TRUE or FALSE
* Expression - is a group of terms (the terms are separated by + or − signs)&#x20;
* Relational operators - < , > , >=, <=, and, or

### Planning Notes and Materials

|                                                            Planning Notes                                                           |                                     Materials                                     |
| :---------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------: |
| Some of the examples might be too much from some students to copy so have some way students can access the links to your projects.  | <p>Pens/Pencils</p><p></p><p>Index Cards/Half Sheets for Exit Slip (optional)</p> |

### Resources

* NEED VIDEO TUTORIAL FOR PYTHON
* Elif Off the Canvas Starter Code ([Trinket](https://trinket.io/python/2eb97c3299))
* Conditionals on the Canvas Starter Code ([Trinket](https://trinket.io/library/trinkets/c53d1a0b5b))
* Do Now Starter Code ([Trinket](https://trinket.io/python/1e78390475))

### Assessments

**Formative**:

* Do Now
* End of lesson code collection and reflectionr esponses

**Summative**:

* Traffic Light (Upcoming Mini Project)
* Drawing App (Upcoming Unit Final)

### Do Now/Warm Up (5 - 10 minutes)

Find the bug and add comments explaining the solution in the following Do Now Starter Code ([Trinket](https://trinket.io/python/1e78390475)).

Ask students to debug the sketch in order to change the color of the rectangle. There are 2 bugs 1) if statement is missing a curly bracket { 2) rect() must be written after the if statement.

Note: Bug number 2 is an error that will come up often for students who have difficulty with the control flow of a program. Control flow is an essential Computer science concept that students will need to master to create algorithms.

Ask Students to share out their solutions and explanations.

* Why does the rect() function have to come after the if statement?&#x20;
* How can we check for syntax errors**?**

### Elif Off the Canvas (15 - 25 minutes)

Ask students to open and duplicate the Elif Off the Canvas Starter Code ([Trinket](https://trinket.io/python/2eb97c3299)). Explain to students the existence of an 'else if' statement, which in Python is written as 'elif,' and its purpose in a program. We can use 'elif' to add more possible outcomes to our sketches. Since there are often more than two possible conditions that we want to work with, we can instruct the program to perform different tasks based on a range of conditions.

I might want to tell someone that if it's cold they should wear a coat, but I also may want to say:

* "if it's freezing, wear a coat,&#x20;
* if it's cold, wear a jacket,&#x20;
* otherwise just wear a sweater."&#x20;

We can do this by adding "else if" to our conditionals between "if" and "else."

```python
if condition 1:
    #block of code to be executed if condition1 is true
elif condition 2:
    #block of code to be executed if condition2 is true
else:
    #block of code to be executed if all conditions false
```

The program will test each condition in order. As soon as one condition evaluates to true, the code inside those brackets is executed and the program continues after the statement.

Then code along with them a conditional to check the variable movie. If `movie` is ‘Ratatouille’, say ‘that movie is about a rat.’ Else if the movie is ‘Tangled’, say ‘That movie is about some hair.’ Otherwise, say ‘I don’t know that movie.’

The finished result of the code-along should look like this:

```python
if movie == "Ratatouille":
    print("That movie is about a rat.")
elif movie == "Tangled":
    print("That movie is about some hair.")
else:
    print("I don't know that movie.")
```

Once students have completed this, test by changing the value of the variable to get different outcomes. Then, explain that you can have many else if conditions. Then, ask students to complete one large conditional that will tell the user when their birthday is based on their sign. (They should plan for EVERY sign!)

Control flow is very important here because else if will check for multiple conditions but will only execute the first condition that is satisfied and stop then stop checking unless a new if statement is written. Using console.log() to debug and test the conditionals. Commenting is vital for this part. The traffic light problem will help reinforce this idea.

### Elif On Canvas Lesson (15 - 30 minutes)

Next, students will move to working with conditionals on the canvas. This should be an easy extension to what they were doing before, except now the variables they make will change values to adjust what is happening on the canvas. Ask students to duplicate the Conditionals on the Canvas Starter Code ([Trinket](https://trinket.io/library/trinkets/c53d1a0b5b)).

Walk students through how to create a variable to control the fill of their circle, and then write a conditional that will change the value of that variable based on mouse position. Once you are done, the conditional for this section should look like the following:

```python
#Remember to announce you're using a global variable 
#in your draw function!

if mouseX > 200:
    circColor = color(255, 255, 0)
elif mouseX < 200:
    circColor = color(255, 0, 255)
else:
    circleColor=color(0,255,255)
    print("found the exact middle")
```

Once students are done, ask them to repeat this process for the rectangle using mouseY. Circulate to help solve problems as students work, and if time permits, ask students to share their solutions at the end.

As you code along through the other conditional examples ensure that students are:

* Commenting their code.&#x20;
* Using variables in the correct scope.&#x20;
* Using console.log() to debug and test&#x20;
* Saving their sketches with appropriate and clear titles.

### Wrap-Up (\~5 minutes)

1. Students can submit code via a Google Form or by placing their link in a Google Doc if you would like to collect it. If not, have students come back together for a discussion on what struggles they encountered in this activity.&#x20;
2. Students can also lead code alongs or walk through their code with the class.

**Guiding Assessment Questions:**

* What is a boolean statement?&#x20;
* What are the two responses I can get from a boolean statement?&#x20;
* What is a conditional statement and how can I use it in programming?&#x20;
* What was challenging about creating an interactive sketch with boolean and conditional statements? Why? How did you solve the challenge? What was easy?

### Extensions

Have students duplicate and modify their emojis sketches to do the following.

* Change the size of the eyes by moving the mouse to the right side of the canvas else
* The color should change if a second condition is met.&#x20;
* Add comments explaining the purpose of the conditions.
