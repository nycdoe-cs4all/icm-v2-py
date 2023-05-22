---
description: How can I use a class to construct multiples of an object?
---

# U4LA2.1: Introduction to Classes and Objects

### Teacher Notes and Overview

In this lesson, students will build on their prior knowledge - including use of dictionaries - to work towards object oriented programming (OOP). They will begin by considering what classes and objects are and will work into creating their own classes and objects from those classes.

Object oriented programming can be a little confusing at first, so this lesson sequence is a slow build that begins off-canvas and works up to creating things on canvas.

### Objectives

Students will be able to:

* Define objects and classes
* Give examples of real life classes and objects
* Create a class with a constructor function and generate new object instances

### Suggested Duration

\~1-2 Periods (\~45 - 90 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.DL.1** Type proficiently on a keyboard.

### Vocabulary

* **class -** a template of something to be created with specific attributes and actions
* **object -** an instance of a class made from the original template

### Planning Notes and Materials

|                                                                 Planning Notes                                                                |                   Materials                  |
| :-------------------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------: |
| Classes and objects can be tricky - be sure to preview so you have many real world examples ready to help this go smoothly for your students. | No specific materials needed for this lesson |

### Resources

* [Starter Code](https://trinket.io/library/trinkets/198227166d) (Trinket)
* NEEDS VIDEO ON OOP IN PYTHON

### Assessments

**Formative:**

* &#x20;Student Practice Activity

**Summative:**

* Upcoming Mini Project
* Upcoming End of Unit Project

### Do Now/Warm Up (\~3 - 5 min)

Think back to the last lesson where we made things bounce - what if you wanted to make _many_ things fly around the screen and bounce? What if you wanted to make at least a hundred?&#x20;

What could you try to make this happen? What would be difficult or frustrating about this process?

<figure><img src="../.gitbook/assets/giphy.gif" alt=""><figcaption><p>Image of woman sitting amidst many bouncey balls</p></figcaption></figure>

### Introducing: Classes and Objects (10 - 15 minutes)

Students should rightfully feel like it would be annoying to manually create that many object literals and program them all to bounce. Some students may realize they could use for loops - both to generate the object literals and to animate them - but that is a stretch at this point in their learning.

What they should start wanting is to create something that will make many versions from the same template. In the example, this would be many bouncing balls - they each have the same shape and behavior, but they may exist at different places on the canvas/have different speeds/colors/etc. Luckily, Python has something that will make this easy: the class and object.

Classes allow us to generate _objects_ which are based off of the blueprint of the class. We can think of a **class** as the template of something that should be created. That something is an **object** which has specific attributes and actions they can do. The **object** is the instance of a **class**.

An easy example is a waffle maker and a waffle. The Waffle Maker here represents the _class_ - as long as you give it batter, it will create a perfect waffle in that size and shape. The waffle itself is the _object_ and while it's always a waffle, it can vary by the type of batter you put in, the cook time, the color, etc.

<figure><img src="../.gitbook/assets/giphy (1).gif" alt=""><figcaption><p>Gif of waffle maker getting batter and creating a Ninja Turtles waffle</p></figcaption></figure>

Another easy example are cars. There is a **car class** which is a general type of car that we understand to have an engine, four wheels, windows, breaks, a steering wheel, etc. But specific instances from that class are unique - those are our **car objects**, like pointing to a specific car or model (think VW Beetle, Toyota Camry, etc). Cars are more complex than the waffle example, but they still have things in common that come from the class and things that vary in each instance.

**Pause here and ask students:** what are things in your life that may be an object made from a class, like the examples we just gave? _This is super common in programming, so it could be things that are tech related - Tiktoks are an example of an object where the video varies, but they still have a like count, comments tied to the videos, a creator name, a caption, etc._

Give students think and potential discussion time and then ask them to share out. These are great responses to capture on chart paper or in slides so that you can refer back to them later if students feel like they need more clarity.

### Creating a Class (10 - 15 min)

For this example, we are going to be considering minions. What characteristics make minions different? Display a few pictures, then come up with a list.

**NB:** _Minions are fun, visual, and relatively topical; if you need more images, just google search 'minions despicable me' but you could substitute this with any other accessible reference you'd like._ [_Zoombinis, anyone?_](https://en.wikipedia.org/wiki/Logical\_Journey\_of\_the\_Zoombinis)

<figure><img src="../.gitbook/assets/image (4) (3).png" alt=""><figcaption><p>Image of three minions with different features</p></figcaption></figure>

You may have a list of features that looks somthing like this:

* Name
* Number of eyes
* Color
* Evil/Good
* Job
* Hair
* Outfit

Or similar, depending on what your students think up! Then, let's dive into creating a Minion class for this example. Open up the starter code ([Trinket](https://trinket.io/library/trinkets/198227166d)) which has space at the top for the code along task.

We will begin by declaring that we are making a class in our code and giving it a name. We are also going to put in the `__init__` (two underscores on each side) function, which is the function that automatically runs to create our object to the class specifications whenever a new object is made. Each class MUST have this to create new objects!

```python
#Define the class
class Minion:
    #define the __init__ method
    def __init__(self):
        #we will initialize features here
```

As with other structures we've seen in Python, we utilize white space to determine what is included in our class, and what is included in our `init` function. Note that it has one parameter in the function - self. This will exist for all of our classes, and it allows the class to reference itself in creation of future objects.

Now, let's start out by adding an attribute that must be true of all minions - let's say that their color is always going to be yellow. To name the attribute in the class, it would look like:

```python
#Define the class
class Minion:
    #define the __init__ method
    def __init__(self):
        self.color = "yellow"
```

See the `self.`? That is new and unique to creating attributes in classes/for objects! Essentially, it says that this isn't just any variable, it's the variable for _this class it**self**_ and _this instance as an object it**self**._ We have to use the **`self.`** in order to make things work correctly.

So far, so good, and as minions _are_ very yellow, this works great. But what about minion attributes that are different, like perhaps their name, or height? For that, we need to add parameters to our `__init__()`. Just like in our other functions, these are values that we input when we call the `__init__` - in this case when we make a new object - that will then become a part of that object. For us, it would look like this:

```python
#Define the class
class Minion:
    #define the __init__ method
    def __init__(self, theName, theHeight):
        self.color = "yellow"
        self.name = theName
        self.height = theHeight
        
```

Here, we are saying that we will feed `theName` in when we make the object, but that value will serve as **`self.name`** for this specific instance of the class. Ditto with `theHeight`! This can all be a little confusing, but as with many things, it will make more sense with practice.

Before we add more attributes, let's try to create a minion and make sure that this worked:

```python
#Define the class
class Minion:
    #define the __init__ method
    def __init__(self, theName, theHeight):
        self.color = "yellow"
        self.name = theName
        self.height = theHeight

#Initialize the first object and save it to a variable
minion1 = Minion("Steven", 2.5)

#We can test if it worked by printing our variable value to the console
print(minion1)
```

When we print this, we should see an object with each value saved. If we don't see this immediately, we can use the arrows in our console to navigate to the appropriate information. If we wanted to access just _some_ of an object's information instead of all of it at once, we could do this:

```python
#Define the class
class Minion:
    #define the __init__ method
    def __init__(self, theName, theHeight):
        self.color = "yellow"
        self.name = theName
        self.height = theHeight

#Initialize the first object and save it to a variable
minion1 = Minion("Steven", 2.5)

#We can test if it worked by printing our variable value to the console
print(minion1)

#Get only the minion's name
print(minion1.name)
```

And just like that, you've created your first class and objects from that class! Before beginning the tasks, ask students to add two more attributes - one with a fixed value and one with a value given when the objects are created - and to create a new object and save it in the `minion2` variable. Review as a class before students move into work time!

### Class and Object Student Practice (15 - 30 min)

Once students have practiced with the minions, they can continue into the starter code to complete the challenges of making other new classes and object instances from each class. The practice is leveled - students should start with mild and only advance once they've completed a working version. You can ask students to collaborate or work independently to complete the assignment.

### Wrap Up (5 - 10 minutes)

Spend some time reviewing answers to the student practice - you may want to share solutions or have students share what they came up with as well as any struggles they experienced or common questions that came up during the activity.

### Extensions

Classes and objects can be tricky, and we have only started looking at a very small amount of what they can do. Consider having students think on places in prior projects they could implement this rather than racing ahead to try a new and more difficult piece of programming.
