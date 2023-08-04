---
description: How can I create a library to store my custom functions?
---

# U1LA5.1: Your Custom Function Library

### Teacher Notes and Overview

In this lesson, students will share what they created in the last mini-project by sharing the code itself for others to use. This is a great skill to learn that collaboration does not need to look like pair programming, and it's also a terrific time for students to get creative!

This will also introduce the idea of having multiple files in one program to keep their code organized. Encourage students to follow this practice as much as possible to stay neat and orderly; their main program file should just be the run of the program, and as much as possible we should hide our (working) functions away so they don't get accidentally messed with and also do not clog up our screen.

### Objectives

**Students will be able to:**

* Import libraries from other Python documents
* Store functions in a separate Python document
* Share custom functions
* Utilize the functions of their peers

### Suggested Duration

1 Period (\~45 minutes)

_This could easily become a two-period lesson if you would like students to spend more time creating with the functions they were given. Please plan accordingly!_

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.5** Modify a function or procedure in a program to perform its computation in a different way over the same inputs, while preserving the result of the overall program.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

**Library:** a document that contains a bunch of functions

### Planning Notes and Materials

|                                                                               Planning Notes                                                                               |                     Materials                     |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------: |
| This requires students to use code from the past mini-project. You may want to create a sample, or use past code, for any students who have been absent or did not finish. | _No additional materials needed for this lesson._ |

### Resources

[Custom Functions Library Template](https://docs.google.com/document/d/1bR9zA3v2dURl3GDlJexQrXrYsyCv1d1PG6d9IwtHPnM/copy)

[Custom Functions Libraries](https://youtu.be/eT8\_oi7FfmQ) (Youtube Video)

### Assessments

**Formative:**

* Custom Function Library Project

**Summative:**

* Abstract Album Art (Upcoming Unit Project)

### Do Now/Warm Up (\~2 - 3 minutes)

Ask students to open their custom emoji and also a tab with a fresh project in Trinket (or whatever editor you choose to use). Depending on the time allotted, students can make any final tweaks to their emoji functions. (Stress that this is the _function_, not the design they made with it that they will be adjusting!)

### Creating Documentation (\~5 - 10 minutes)

Since the start of the year, you've been using functions written by other people and _documentation_ that explains how they work. It is always a best practice to leave documentation in your code - and especially within your function - with the assumption that someone else might be using your code one day. (And, honestly, that someone else might just be Future You.)

An easy way to do this is to leave a special kind of comment called a docstring at the top of your function. In some code editors, this will auto-generate helper text that explains the function when you start using it! We want to describe not only what our function does, but what the inputs do, as well. And we should add our name for good measure! So if we use the very first `happyFace()` function we wrote, the documentation might look like this:

<pre class="language-python"><code class="lang-python">def happyFace(xPos, yPos):
    """
    Draws a happy face emoji.
    xPos controls x position of emoji.
    yPos controls y position of emoji.
    Made by Your Name.
    """
    
<strong>    strokeWeight(1)
</strong>    fill(169, 222, 183)
    ellipse(xPos,yPos,100, 100) #125, 200
    arc(xPos-15,yPos,25,25,radians(180),radians(360))
    arc(xPos+35,yPos,15,25,radians(180),radians(360))
    arc(xPos+11,yPos+26,40,10,radians(0),radians(180))
</code></pre>

**NB:** _Eventually, they should also describe the return of a function, but that is not necessary yet as their functions do not have return values and it would be a lot to explain!_

Ask students to take a moment to _document_ their function by writing a multi-line comment directly above it. It should include one line to explain what the function does, and then explanations for any and all parameters.

### Sharing Functions && Documentation (\~7 - 12 minutes)

Share students on the [Custom Functions Library Template](https://docs.google.com/document/d/1bR9zA3v2dURl3GDlJexQrXrYsyCv1d1PG6d9IwtHPnM/copy).

Please note that you should just make one per class - in especially large classes, you may have students do this in batches.

Ask students to copy/paste their documentation and function into the document. Remind students not to style the font - it is currently set to a monotype font which generally copy/pastes well into code editors! (Other fonts can do strange things with formatting.) At this point, ask students to change their emoji name _just in this document_ to include their first name before it, such as `courtneyHappyFace()`.

Eventually, students will be creating their own function library, and functions must be uniquely named to work as expected!

From there, have students go to the blank project they opened as part of the do now. They will be creating a new Python file to house their functions and linking it to the project so it's usable. This section is best done as a code-along!

<figure><img src="../.gitbook/assets/Screen Shot 2022-11-17 at 11.45.31 AM.png" alt=""><figcaption><p>Trinket editor screen grab showing buttons to add files.</p></figcaption></figure>

In Trinket, click the **+** button which will say 'Create text file' when you hover over it. Once you do so, you'll create a new file - name it functions.py. Note that it MUST have the .py otherwise the computer will not recognize this as a Python file!

<figure><img src="../.gitbook/assets/Screen Shot 2022-11-17 at 11.46.57 AM.png" alt=""><figcaption><p>Screenshot of Trinket with a new file added called functions.py</p></figcaption></figure>

Now, we need to connect the two files, but first, let's load in some functions. Have students start by copy/pasting their own emoji function into the functions.py document. _(We will have time to add more functions later, but this is enough to get us started and make sure our linked files communicate.)_ Because our functions rely on the Processing.py library, we will also need to add a line at the top:

```python
from processing import *
```

And now it's time to learn what that means and why it's important! Let's head back to our main.py file.

Python has a lot of libraries - some external, and some internal like our funcitons.py sheet - that we can use in our main programs. There are a few ways to do this. The first is to use `import`, which will allow us to import everything in functions.py.

Using `import` would look something like this:

```python
from processing import *
import functions


def setup():
    size(400,400)


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    functions.happyFace(200,200)
    

draw = draw
run()
```

Now, a few things for us to notice: first, we imported the library at the top of our page. This will always be our practice so we can use the functions for the entire program. When we called our function, we had to write `functions.happyFace()` - this is so the program knows where to find the function definition. As we can imagine, this can get annoying! One way to get around it is to save an instance of a function to an alias, which we don't need to cover now since we have a few other options.

Rather than using `import`, we can use `from`. `from` has two distinct uses. In the first, we use it only import select functions:

```python
from processing import *
from functions import happyFace


def setup():
    size(400,400)


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    happyFace(200,200)
    

draw = draw
run()
```

Now we don't need to use functions. because `happyFace()` has been locally scoped! But what if we have _a lot_ of functions to use? Well, we can look at how processing has been imported as a reference. If we do something like this:

```python
from processing import *
from functions import *


def setup():
    size(400,400)


def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    happyFace(200,200)
    

draw = draw
run()
```

...we will have access to _all_ of the functions in functions.py! This is great if you are using most of a library. If you are not, stick with the plain `from` as it will save a little bit of processing room in your program.

But for now, we need to fill up our library with more functions.

### Using Your Custom Function Library (10 - 15 minutes)

Ask students to identify several functions they want to use and copy/paste each into their functions.js file. They should use these to create an interesting composition in their new project. Remember to save to use this as a reference later!

### Wrap-Up (\~5 minutes)

_There are no planned extensions for this lesson. Students should keep creating with the given functions, but they can also modify functions to make their own version!_
