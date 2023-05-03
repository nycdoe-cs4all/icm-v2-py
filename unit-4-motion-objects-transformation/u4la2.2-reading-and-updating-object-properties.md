---
description: How can I read and update properties/attributes of an object?
---

# U4LA2.2: Reading and Updating Object Properties

### Teacher Notes and Overview

This lesson builds on what students started in their introduction to objects; it specifically focuses on their ability to read and update object properties in a fairly straightforward, off-canvas practice activity. It's short and meant to reinforce their prior learning.

### Objectives

Students will be able to:

* Read values from an object
* Update values contained within an object

### Suggested Duration

1 Period (\~45 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.DL.1** Type proficiently on a keyboard.

### Vocabulary

_No new vocabulary is introduced_

### Planning Notes and Materials

|                                                                Planning Notes                                                                |           Materials          |
| :------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------: |
| This is a relatively straight forward lesson; make sure you've reviewed any errors from the previous day as it leaves space to review those. | No specific materials needed |

### Resources

* [Starter Code](https://trinket.io/library/trinkets/5c082734e7) (Trinket)
* NEED PYTHON READING/UPDATING OBJECTS VIDEO

### Assessments

**Formative:**

* Student Practice Activity

**Summative:**

* Upcoming Mini Project
* Upcoming Unit Final Project

### Do Now/Warm Up (3 - 5 minutes)

Display this Class to your students and ask them to come up with the following:

1. Which properties/attributes are default values?
2. What information do you need to provide when making a new object?
3. How would you create a new object from this class?
4. What would need to happen if you wanted to create a `homeroom` property, assuming each student instance will have a different homeroom?

```python
class Student:
    def __init__(self, theName, theGrade, theFavClass):
        self.name = theName
        self.grade = theGrade
        self.school = "CS University"
        self.favClass = "Art"
```

**NB:** _This example is a little tricky, as `theFavClass` isn't actually used anywhere in the `constructor` - so technically, objects could be generated without, and `favClass` is actually a default value._

### Classes Clean-Up (5-10 minutes)

Depending on what you noticed in the previously lesson, you may want to spend some time reviewing any common syntax or conceptual mistakes students are making with classes and objects. A few common ones to look out for:

{% code overflow="wrap" %}
```python
#Writing the init function without (), which mark it as a function
class Student:
    def __init__:
        self.school = "CS University"
        self.favClass = "Art"
        
#Any other init related typos:
class Student:
    def init():

class Student:
    def _init_():

#Forgetting : at any level:
class Student
    def __init__(self, theName, theGrade, theFavClass)
        self.name = theName
        self.grade = theGrade
        self.school = "CS University"
        self.favClass = "Art"

#Forgetting self, or using a , when it should've been a .
class Student:
    def __init__(theName, theGrade, theFavClass):
        name = theName
        grade = theGrade
        self,school = "CS University"
        self,favClass = "Art"

#Any other variety of typos! It may also be useful to review the difference btween a Class and a single object, and specifically the idea that class names are Capitalized while variables holidng objects are not.
```
{% endcode %}

You may want to review all of these, or you may want to focus in on issues that were more specific to what you were seeing from your students.

### Update Properties of an Object (5- 10 minutes)

We can think of every property/attribute within an object as it's own individual variable - anything that you can or have done with a variable before, you can do with any single value from an object. That means that just as in the past we have changed values of variables, we can change the values of properties within our objects.

To do this, we use the dot syntax to access the property - we saw this yesterday when printing out out specific values from the objects we had created.

Let's give it a try by creating a new class and an object from that class.&#x20;

In this example, we are going to make a class called `SubwayStation`. Every instance of this class will have a name, borough, subway lines (as an array), and an elevator property, which we will default to false because [the MTA has some accessibility issues](https://www.nytimes.com/2022/06/22/nyregion/nyc-subway-accessibility-disabilities-elevators.html).

Begin by opening a blank editor and build out the following:

```python
class SubwayStation:
    def __init__(self, name, borough, lines):
        self.name = name
        self.name = borough
        self.lines = lines
        self.elevator = False
```

Now, let's create an instance of this class. We are going to do "161 St - Yankee Stadium" in our example, but you should select any subway station that is near your school or important to your student population.

```python
class SubwayStation:
    def __init__(self, name, borough, lines):
        self.name = name
        self.name = borough
        self.lines = lines
        self.elevator = False

yankeeStadium = SubwayStation("161 St - Yankee Stadium", "Bronx", ["B", "D", 4])

#let's test that it worked!
print(yankeeStadium)
```

This should all be review from yesterday. But let's say that we learn that this station actually _has_ an elevator (or one was added, or one got fixed), so the `elevator` property actually needs to be marked as `true`. We don't need to start over! We can update that property, like so:

<pre class="language-python"><code class="lang-python">class SubwayStation:
    def __init__(self, name, borough, lines):
        self.name = name
        self.name = borough
        self.lines = lines
        self.elevator = False

yankeeStadium = SubwayStation("161 St - Yankee Stadium", "Bronx", ["B", "D", 4])

#let's test that it worked!
print(yankeeStadium)

#change elevator value
yankeeStadium.elevator = True
<strong>print(yankeeStadium.elevator)
</strong></code></pre>

This should look very familiar to how we have updated variable values in the past. We can do this for _any_ property, whether it was a default value or a value we gave when creating the new object.

### Updating Values: Student Practice (15-25 minutes)

In this practice, students will utilize a [starter code](https://trinket.io/library/trinkets/5c082734e7) with a series of challenges asking them to access information from an object and also update that information. As always, students can work collaboratively or independently to complete these activities.

**NB:** _In this example, the Class has been created for them and hidden, along with all of the object instances, in another python file. You can see the file at the top of the screen and see it imported in line 1. This is a great thing to teach students as they continue to create more and more complex projects, sicne their code may become overwhelming if they leave it all in a single document._

### Wrap-Up (\~5 min)

As in the last lesson, this is a great time to use the wrap-up to review some solutions to the student practice, or review common mistakes. If students worked through it fairly quickly, the majority may want to discuss the spicy challenge option at the end to ensure they know how to complete it.

### Extension

Once again, this is a fairly compact lesson without a lot of extension - largely on purpose, as we want to introduce classes and objects slowly to prevent confusion. Ask students what else they would add/change to the class they are working with to make it more useful!
