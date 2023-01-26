---
description: How can we use iteration to abstract artwork?
---

# U3LA1.1: While Loops

### Teacher Notes and Overview

This lesson introduces repetition using while loops. Students will create a sketch with a repeated element to fill a specific space.

While loops is a great introduction to loops because of the syntax for declaring, conditional checking and incrementation are not as complicated as it is for a for loop.

Common misconceptions are forgetting to increment the variable, writing a valid condition and forgetting to use curly brackets. It is always important to have students write comments to debug their code.

This pair-programming experience is very open-ended - try to encourage students to talk together about features for their program, rather than each person deciding for the group when it is their turn to navigate.

Push students to think about the user experience in leaving their feedback: did they know while loop is working correctly? How could this be improved?

### Objectives

Students will be able to:

* Explain how the components of the while loops are essential to efficiency
* Create while loops
* Use while loops to generate multiple shapes

### Suggested Duration

45 Minutes (\~1 period)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.8** Develop a program that effectively uses control structures in order to create a computer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **loop** - a sequence of instructions that is repeated until a certain condition is no longer met.
* **iteration** - the repetition of a process
* **while loop** - a control flow statement that allows code to be executed repeatedly as long as the condition is true
* **control structure -** a block of code that specifies the flow of a program according to specific conditions

### Planning Notes and Materials

|       Planning Notes       |           Materials          |
| :------------------------: | :--------------------------: |
| No specific planning notes | No specific materials needed |

### Resources

* NEED VIDEO FOR WHILE LOOPS AND PYTHON
* [Python While Loops](https://www.w3schools.com/python/python\_while\_loops.asp) (W3 Schools)
* While Loop w/ Code Comment Sample ([Trinket](https://trinket.io/python/078621d49d))
* Spicy Challenge Example Code ([Trinket](https://trinket.io/library/trinkets/281ece669b))

### Assessments

**Formative:**

* Do Now Task
* Coding Exercises
* Wrap Up Assignment

**Summative:**

* Create A Wallpaper (Upcoming Mini Project)

### Do Now/Warm Up (\~5 - 7 minutes)

_Have students create 5 equidistant ellipses._

Open a new sketch, name it U3LA1 While loops and recreate the image below

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p>A row of five equally spaced, congruent ellipses</p></figcaption></figure>

Ask students to do the following:

1. Add 5 more ellipses to the current row, they will most likely get frustrated because they will have to keep the ellipses equidistant.
2. Answer the prompt: how we can call the ellipse function more efficiently? Push their thinking to think about why loops are necessary.

### Repeat Shapes with a While Loop (\~15 minutes)

From this Do Now, ask students how could they code their loops effectively? Students might talk about copy/pasting lines of code, adjusting only selected numbers, etc. Most, if not all students, probably came to a solution like so:

```
def draw():
    background(220)
    ellipse(100, 60, 40, 40)
    ellipse(200, 60, 40, 40)
    ellipse(300, 60, 40, 40)
    ellipse(400, 60, 40, 40)
    ellipse(500, 60, 40, 40)
```

But this is a lot of repetition, and something that students should start getting used to is if something looks like it repeats frequently, there is probably an easier, or at least more efficient, way to handle it in our code.

Talk students through the actual process that you are following, which is something to the effect of:

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>Handwriting that describes the loop of drawing ellipses and moving right.</p></figcaption></figure>

Essentially, we are are drawing a new circle every 100 pixels, and we may be tempted to write a conditional statement that says something to that effect. However, students will find this conditional doesn't work as intended, and that is because conditionals are not meant to act as loops. Conditionals run once, and once the condition is met, they stop running. (Albeit in the draw function, which is called repeatedly, it can appear as if the loop is repeating.)

Luckily, there is a control structure that can help us do this! Introducing the while loop: a loop that only runs WHILE a certain condition is true, and stops running once it ceases to be true. It looks something like this in the draw function:

```
x = 100
while x < width:
    ellipse(x, 60, 40, 40)
    x = x + 100 #or x+=100
```

There are three steps needed to make sure our loop works correctly:

1. We **declare and initialize a variable**. Initializing a variable is setting the initial value for that variable, or where you want it to start. In this case, we would like to it begin at 100 pixels.
2. We **check whether it meets a condition**. The condition is inside the parentheses. We want to execute the code in the brackets on condition that x is still less than the width of the canvas.
3. We **change the value of that variable in a way that will eventually make it meet the condition**. In the code below, 100 is added to x inside the brackets. Every time the code is run x will increase by 100 until its value is larger than the width of the canvas. Then the loop will be completed and the program will move on in the code.

This ensures we don't create an infinite loop, which will certainly crash our browsers. Be prepared for browser crashes - make sure students DO NOT have the AutoSave feature selected as it might refresh before their loops are done. When students inevitably crash everything, cheer for them! They know enough code to break something!

Code this for loop with students so that they have an example saved in their account. (They can comment out previous ellipses from the Do Now.)

The big benefit of loops is that not only does it make our code cleaner and more efficient, but our code is now easy to change, customize, and update. If we want the row of ellipses to start somewhere else, we can adjust the starting variable. If we want to increase or decrease the spacing between the ellipses, we can adjust what we add to x. And we can change the circles themselves without having to make edits to multiple places in our code! Give students 2-3 minutes to just play with numbers and add shapes/features to their loop - it's important they understand the loop can do more than just draw one repeated shape.

### Student Practice and Play (15 - 20 minutes)

After students have had a chance to experiment with the code from the lesson section, send students to work either individually or in pairs/small groups, based on your classroom. (We STRONGLY encourage collaborative pair or group work to help students grow their soft skills as they learn to code!)

Instruct students to use the while loop to do the following (and be on the lookout for curly bracket errors, and multiple while loop errors):

* Start a row at the left end of the canvas
* Draw a row of ellipses 50 pixels apart
* Draw ellipses only on the left half of the canvas

For students who need an extra spicy challenge, ask them to try to recreate one of the following in their while loop. Make sure they understand they only need ONE while loop - and that they should use functions to help them!

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption><p>Row of concentric, differently colored circles looking like targets.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p>Row of red 😐 faces.</p></figcaption></figure>

**Alternately, or in addition, students may take a design they have created previously and try to get it to repeat in a while loop, or build a new custom design that will be repeated.**

### Wrap-Up (\~5 minutes)

Ask students to post their project links in a forum such as Slack or Google Classroom. Then, have them view and comment on two other projects, leaving a glow and grow for each

Guiding questions:

* How do while loops make the code more efficient?
* Explain the parts of a while loop. Why are they important?
* What was challenging about using a while loop?

### Extensions

Give students specific and logically challenging tasks for while loops such as:

* Repeating their emoji from unit 1
* Creating a grid of ellipses
