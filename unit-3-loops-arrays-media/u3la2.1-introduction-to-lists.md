---
description: How can lists help us simplify code?
---

# U3LA2.1: Introduction to Lists

### Teacher Notes and Overview

In this lesson, students will be introduced to the concept of lists.

Lists are an important and useful concept in computer science as they allow us to easily store a lot of information in an orderly fashion. (And they will be used in many future lessons!) Lists can be confusing to students when it comes to calling index values to access elements of the list because computers begin counting at 0. It would be good to create multiple list examples and then have students call the elements by either hard coding the number or using a variable. Students will have an opportunity to integrate through a list using a for loop in a later lesson.

**Note:** _In other languages, such as JavaScript, lists are often referred to as 'arrays.' In Python, an array is a separate data type that is part of the NumPy library._

### Objectives

Students will be able to:

* Explain how a list can be used instead of multiple variables&#x20;
* Create lists&#x20;
* Retrieve information from lists

### Suggested Duration

1-2 periods (\~45-90 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.7** Design or remix a program that utilizes a data structure to maintain changes to related pieces of data.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **List** - an ordered series of data&#x20;
* **Index** - a position within an list&#x20;
* **Zero-Indexed** - The first element of a list has an index of 0, not 1
* **Element** - a piece of data in a list&#x20;

### Planning Notes and Materials

|                                                     Planning Notes                                                    |           Materials          |
| :-------------------------------------------------------------------------------------------------------------------: | :--------------------------: |
| There are no specific planning notes for this lesson, but it is the first lesson students will be using media - whoo! | No special materials needed. |

### Resources

* NEED A VIDEO ON LISTS IN PYTHON
* Colors in Lists Starter Code ([Trinket](https://trinket.io/library/trinkets/d30c563050))
* [Python Lists (W3 Schools)](https://www.w3schools.com/python/python\_lists.asp)
* [Arrays Information - Code.org (Youtube Video)](https://youtu.be/seBDTeZmb-k) _NB: This is JavaScript, but many concepts are the same!_

### Assessments

**Formative:**

* Do Now Discussion
* Ability to Create and Read arrays during the learning activity
* Explain benefits of arrays in the Wrap Up

**Summative:**

* Fortune Teller (Upcoming Mini Project)

### Do Now/Warm Up (\~3-5 minutes)

Ask students to describe what makes lists useful in everyday life with the following question prompts:

* What makes a list useful?&#x20;
* How would lists be useful in programming?&#x20;
* How can we use lists in p5.js?

_Discuss with students possible answers:_

* _Lists help us organize information._&#x20;
* _Lists help us collect all the relevant information in one place._&#x20;
* _Lists show that a lot of ideas are related._&#x20;
* _Lists help us order or prioritize ideas._&#x20;
* _Lists help us think about the big picture_

Tell students that we will be creating and using arrays which are the same concepts of lists in real life.

### What Are Lists? _Grocery Store Example (\~15 minutes)_

Computer scientists spend a lot of time thinking about information. After all, computers are just tools to manipulate pieces of information in certain ways. Before computers were around, humans invented lots of different ways to store information. The library was given the Dewey Decimal system, in which numbers were associated with the information in certain books. That’s a pretty complicated way of storing information.

But one way of storing information that you’ve definitely used before is a list. Maybe you’ve made a list of people to invite to your birthday. Maybe you made a list of things to buy at the grocery store. Something useful about lists is that they’re one object themselves: you don’t have to carry around a lot of different scraps of paper containing the name of everything you want to get at the store. You can just carry the list. And lists can change - you can cross something off a list, add something to a list, or replace one element with another. Luckily for us, lists exist in Python just as they exist in real life!

When dealing with lists in computer programming, we typically talk about **c**reating, **r**eading, **u**pdating, and **d**eleting from list, or the acronym **CRUD.** Today, you will focus on **creating** and **reading**.

**Ask students to take thirty seconds to write down a few items they want to buy at the grocery store (or at Target, if you want more options). Then, ask students to share out a few while you make a list on chart paper/white board.** Aim for the list to be \~10 items long. Title the chart paper **`groceryList`** and then explain to students that this is a list of objects that, paper permitting, could be as long as the want it to be, and have a certain and specific order they have been saved in.

Explain to students that this `groceryList` has an order that is defined by something called an _index_ value, or the number we give to each element. Computers are interesting in that they start indexing at **zero** instead of **one**, like we may be used to. **On the chart paper, number each item 0 - however many items you have.** Then give this scenario to students: _You're shopping with a parent and have a lot to get - they could hand you the list, or tell you 'go get bread,' but they could also say 'Go get item 2. Go get item 0' etc. If I asked you to go get item 1, what would you come back with? What about item 4?_

Ask a few rounds of these (_'go get item...')_ questions, taking student answers and asking them to explain. Using 1 and 0 may trip up students which is perfectly natural - just review and make sure they understand the numbering system used in Python! When students have gotten the hang of retrieving items with an index value, ask them "What is the length of this list?" Anticipate that most students will look at the last number - for example, 9 - and say that. Remind them that there is also a 0 value and demonstrate counting how many items there are if necessary! Explain to students that a cool thing about arrays, in addition to making our code simpler by holding lots of things in one place, is that traits about them, like length, get stored in the program and we can access with simple commands that we will talk about later.

Once students have done a little practice, it's time to turn this example into code before moving to example 2. This is our '**create**' list action. Ask students to open a blank editor and code along the following, using whatever you wrote on your chart paper as a model:

```python
groceryList = ["bread", "orange juice", "pasta", "rice", "beans",
"pizza", "bananas", "coconut", "potatoes", "spinach"]
```

Explain the pieces needed to make this list. By now, you should understand what a variable is. It’s a name that you give to a piece of data or information. You can change the value of the variable, but the name will always stay the same. With lists, we can store many separate values in one variable name. To indicate that a variable holds a list, we put all of the items inside square brackets, with each element separated by a comma. Arrays themselves are a data type that can hold many different _types_ of data - this one is currently holding strings, but they could hold colors, numbers, objects, even other lists!

If students need more of an example of how arrays work, consider this:

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption><p>Diagram of an array explaining name, elements, values, etc.</p></figcaption></figure>

Please note for students: the elements in this list are strings, or letter characters all put together, which is why they are in quotation marks. If we were storing numbers, p5.js colors, or other specific data types, the quotations wouldn't be needed!

Once the list is in your code, review with students how you can **call** (or '**read**') items of a list using the **list name** and the **index value, like so: `groceryList[3]`.** You can do this either with `print()` or `text()`, depending on your preference for showing in the console or the canvas and what works best for your classroom.

```python
from processing import *
from collide2d import *

#NOTE: For consistency, we are making this a global variable at the top of our code.
#In this example, you could also create the list in draw as it has no need to be global.
#Use your discretion in teaching kids and if they have generalized these ideas or if it would confuse them!

groceryList = ["bread", "orange juice", "pasta", "rice", "beans",
"pizza", "bananas", "coconut", "potatoes", "spinach"]

def setup():
    size(520,300)

def draw():
    global groceryList
    
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    text(groceryList[3], 200, 200)
    #alternately, print(groceryList[3]) would display to canvas
    #this method could happen outside of setup or draw!
    
draw = draw
run()
```

Run a few times, changing out the index value each time. Before running, always ask students to predict what will display.&#x20;

Similarly to the chart paper example, after a few iterations of calling single items from the list, demonstrate that you can also pull other data from the list by trying things like this:

```python
print(len(groceryList))
```

It's okay if students don't see a ton of use in this feature yet - you can brainstorm some places where that might be useful, or just let it ride until future lessons.

Once they feel comfortable, it's time to hit them with another example!

### What are lists?: _Building Example_ (15 minutes)

Since lists are a whole new code concept, we like to give students a few ways to process them in hopes that one will resonate and stick around in their brains. Explain to students that you are going to put the grocery list aside for a moment and think about lists in a different way.

Think of variables and lists like buildings. Let’s say you want to count the number of people on each floor of a building. If the building only has one floor, it’s easy, right? You can just say “The building has 30 people in it.” But if we’re thinking about the Empire State Building, it’s harder than that. You need to find a way to talk about the number of people on each floor of the Empire State Building.

So how would you say that in real life? You’d probably say something like “There are 20 people on the first floor, 30 people on the second floor, 32 people on the third floor…” and so on. And we all know you’re talking about the same building, the Empire State Building, you’re just referring to each floor separately.

So you can think of a list as something similar. It’s a bunch of different values, but with the same name. And we write it in a similar way as we would talk about buildings with floors. If we had a variable that held the number of people on the ground floor of a single-story building, the declaration might look something like this: `building = 30` But if we’re talking about a building with many floors, our list might look like this: `building[0] = 25`; `building[1] = 40`, `building[2] = 30`.

Notice the ‘\[ ]’ after the name of our variable? That’s where we put the index, or number, of the element, or specific value within the array, that we want to access or change.

**Let's assume in this example, each person icon represents 10 people:**

<figure><img src="../.gitbook/assets/image (1) (7).png" alt=""><figcaption><p>Image of simplified building with floor numbers labeled and people on each floor.</p></figcaption></figure>

Using the syntax, and assuming this is the building we’re talking about, what would `building[3]` be equal to? What about `building[1]`?

You may have noticed something weird. When I was declaring values in the array, I started with `building[0]`. Why did I do that, and not start with `building[1]`? Because in p5, arrays are zero-indexed, which means they start at zero. Think of it like a building that counts the ground floor as zero and starts counting at one after you’ve gone up a floor.

If we wanted to make an array that held the amount of people per building floor, it might look like this:

```python
buildingPop = [50, 0, 20, 40, 10]
```

...and we could then call those numbers in our program to control whatever we wanted!

### Colors in Lists and Practice (20 - 30 min)

After all of those examples, it's time to see one last application of lists - this time instead of numbers or strings, let's try putting colors into a list. For this activity, we are going to imagine we are making a color palette for a design project (something that graphic artists, fashion designers, and even event planners have to do often) using [Adobe Color Picker](https://color.adobe.com/create/color-wheel).

**Share students on this starter code** ([Trinket](https://trinket.io/library/trinkets/d30c563050)). Then demonstrate Adobe Color Picker and select a palette of your choosing. With students, show them how they could create and use an array of colors via the following code along. **NB**: _the `color()` feature is Processing.py specific (it is essentially creating a color object) and so this list, while the variable still needs to be declared globally, above setup, must be given values inside the setup function for the colors to register._&#x20;

Creating the list would look like this:

```python
from processing import *
from collide2d import *

testColors = []

def setup():
    size(520,300)
    global testColors
    testColors = [color(252,214,202), color(217,138,124), 
 color(240,101,89), color(219,117,116), color(255,28,82)]
```

You would then use the colors as we have called other items in the array. Students will need to choose primary and secondary/accent colors based on the palette they create:

```python
fill(palette1[2])
rect(10,50,200,50)
```

### Wrap-Up (\~5 minutes)

Ask students to post their project links in a forum such as Slack or the Google Classroom. Then, have them view and comment on two other projects, leaving a glow and grow for each

Guiding questions:

1. How are arrays useful?&#x20;
2. Describe how to can an array be used on p5.js?
