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
        this.name = theName
        this.grade = theGrade
        this.school = "CS University"
        this.favClass = "Art"
```
