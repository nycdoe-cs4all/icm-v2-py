---
description: How can I add methods to a class to give more functionality to my objects?
---

# U4LA2.3: Methods Off Canvas

### Teacher Notes and Overview

In this lesson, students are introduced to methods within classes. They will work to create methods for two different classes that work entirely off-canvas. In the next lesson, we will reintroduce the canvas and allow students to apply their knowledge of objects to make something visual.

### Objectives

Students will be able to:

* Define and describe methods
* Create custom methods within their classes
* Call methods on objects

### Suggested Duration

1-2 Periods (45 - 90 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

**methods -** functions that are part of a class and can only be utilized by objects of that class.

### Planning Notes and Materials

|                                          Planning Notes                                         |           Materials          |
| :---------------------------------------------------------------------------------------------: | :--------------------------: |
| Be sure to review the starter code so you have an idea of how to address all of the challenges. | No specific materials needed |

### Resources

* [Starter Code](https://trinket.io/library/trinkets/3f983dc0a7) (Trinket)

### Assessments

**Formative:**

* Student Challenge Activity

**Summative:**

* Upcoming Mini Project
* Upcoming Unit Final

### Do Now/Warm Up (3-5 minutes)

Imagine that you were just hired by an online retail company. They've told you that they need to build out their website to create a customer shopping experience, and they want to do this through object oriented programming. What do you think you would need to include in the class so the User can successfully shop?

### Introducing Class Methods (5 - 10 minutes)

After reviewing the Do Now, explain to students that in addition to the properties they may want to store in a User object (name, email, address, credit card info, etc) they probably also want the user to be able to _do_ things. Maybe they can change their address and have it verify with password, or, save favorite items, or add things to their cart, or check out with a coupon.

All of these things represent _actions_ - the kind we usually associate with functions! When we are dealing with Classes and objects, we refer to these functions as **methods.** Methods are a special type of function that are part of a Class and are only usable by objects in that class. We've actually seen this before - when we do `myList.append()`, that `.append()` is actually a method that only works on lists (which we can think of as a special type of object).

So far, the only method we've seen is the `__init__()`. This one is required to create our objects and it runs automatically when we create a new object. Other methods will be specific to the needs of the Class. Let's think back to our `Minion` class. In the `Minion` class, we might have a method called `helpGru()` and we could define what happens when it is called within our class. If we wanted to use that method, it would look like: `minion1.helpGru()`

Today, the focus will be on writing and testing our own methods for different classes. Everything will remain off-canvas - we are still going to be looking at what's coming up in the terminal - for today. _This is strictly to keep us from focusing on making a visual perfect or getting distracted!_ In our next lessons, we will begin applying what we know to our canvas designs!

### Creating Methods: Code Along (10 - 15 minutes)

Ask students to open and duplicate the [starter code](https://trinket.io/library/trinkets/3f983dc0a7). They should see that there is an initial code along followed by a few tests they will be asked to uncomment and try, as well as the rest of the project challenges that they will work on later.

To begin, let's take a look at the Code Along: we are being asked to create a Cart class with some specific properties. We can think of this `Cart` as a class that might work with our User class from the Do Now - we could even have a `Cart` object as a property of the User (what a crazy world)!

To begin, let's build this out together:

```python
class Cart:
    def __init__(self, email):
        self.email = email
        self.total = 0
        self.itemList = []
```

Once this is built and any initial questions ahve been clarified, ask students to independently complete #1-3, which test to see the `Cart` works. Circulate to assist/answer questions as needed, then take a brief poll to make sure everyone has a working `Cart` class and `testCart` object.

We now are asked to make a method called `updateEmail()` - this will seem redundant, as we have learned to change values without a function, but let's do it to get used to syntax. Methods are made within the class, so we will be scrolling back up to our class definition at the top of our code and adding in:

```python
class Cart:
    def __init__(self, email):
        self.email = email
        self.total = 0
        self.itemList = []
    
    def updateEmail(self, newEmail):
        self.email = newEmail
        print("Email updated") #this is optional but a great check to see if things are working!
```

Important things to note:

1. Our methods _still_ need to include self if they are referencing the object it_self_. Otherwise, we follow the normal function structure.
2. **Pay very close attention to the identation!** Remember, this is very important in Python - it determines where things begin and end. By being indented under the Class and inline with each other, we understand the methods to all be part of the same class.
3. We didn't use a return statement - that is because in this example, we aren't dealing with a value from outside our object that needs to be returned back to the program. We are just updating the object itself.

### Student Challenge: Cart and Player Class (15 - 25 minutes)

From here, students will be working to complete the rest of the challenges. As always, you can choose to have them work independently, to pair program with a partner, or to work as part of a small group. While students work, circulate to assist. At any point, if you feel like many students are becoming hung up on the same issue, feel free to pause to review as a class.

### Wrap-Up (3 - 5 min)

Review answers with the class by having students/pairs/groups share some of their solutions or sticking points to talk through.

### Extensions

Students will find a spicy challenge at the end of the starter code that they can use to challenge themselves if they have raced through everything else.
