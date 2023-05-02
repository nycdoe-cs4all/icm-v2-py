---
description: How can logical operators make more specific and complex conditionals?
---

# ✨ U2LA1.3: Logical Operators And/Or

### Teacher Notes and Overview

**NB:** _This lesson technically covers NYS Standard **7-8.CT.8**_ _Develop or remix a program that effectivey combines one or more control structures for creative expression or to solve a problem. However, we know not all schools can guarantee a middle school sequence prior to this course. This lesson can be significantly abbreviated or skipped entirely based on the knowledge your students come in with!_

This learning activity builds on conditional statements using the Logical Operators 'and' and 'or'. Students create a changing background color using a grid for guidance. They will use these concepts as they build a traffic light in the next project.

Students should have a solid understanding of conditionals and how it is satisfied through a boolean. This lesson will focus heavily on creating more complex algorithms through the use of conditionals. Therefore it is important that students add comments to keep track of the sketches control flow. Students will also benefit greatly from peer programming because they can model their thinking behind their code.

### Objectives

Students should be able to:

* Use if, else if and else statements in conjunction with && and ||&#x20;
* Create conditional statements (event handlers)&#x20;
* Elaborate on how to satisfy a condition.

### Suggested Duration

1 period (\~45 minutes)

### NYS Standards

_**7-8.CT.8** Develop or remix a program that effectively combines one or more control structures for creative expression or to solve a problem._

**9-12.CT.8** Develop a program that effectively uses control structures in order to create a computer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* Conditional statements - a set of rules performed if a certain condition is met&#x20;
* Boolean expressions - a logical statement that is either TRUE or FALSE&#x20;
* and - joins two statements to make sure they are both true before the whole statement is true
* or - joins two statements so that if one is true, the whole statement is true

**Pre-Pre Vocabulary**

* Expression - is a group of terms (the terms are separated by + or − signs)&#x20;
* Relational operators - < , > , >=, <=, and, or

### Planning Notes and Materials

|                                                            Planning Notes                                                           |                                     Materials                                     |
| :---------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------: |
| Some of the examples might be too much from some students to copy so have some way students can access the links to your projects.  | <p>Pens/Pencils</p><p></p><p>Index Cards/Half Sheets for Exit Slip (optional)</p> |

### Resources

* And/Or Starter Code ([Trinket](https://trinket.io/python/e0b5c2fe4d))
* NEED VIDEO TUTORIAL IN PYTHON

### Assessments

**Formative**:

* Do Now
* End of lesson code collection and reflection responses

**Summative**:

* Traffic Light (Upcoming Mini Project)
* Drawing App (Upcoming Unit Final)

### Do Now/Warm-Up (5-10 minutes)

Ask students to look at both image 1 and image 2. They have to explain how Jose can eat ice cream with the given logical operator. Then explain the difference between both images.

<figure><img src="../.gitbook/assets/image (13) (1).png" alt=""><figcaption><p>Image demonstrating the 'AND' operator</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (3) (2).png" alt=""><figcaption><p>Image demonstrating the 'OR' operator</p></figcaption></figure>

Note: Creating a chart like the one below may help some students better understand logical operators. Use the images above and the chart in conjunction to explain 'and' and 'or.'

<figure><img src="../.gitbook/assets/image (6) (3).png" alt=""><figcaption><p>Image showing tables of outcomes for values of a/b using and/or</p></figcaption></figure>

Ask students:

* What is the difference between both images?&#x20;
* How is and, and or different?

If students still do not grasp this concept (or if you would just like them to have more practice), have them create their own conditions and explain it to a peer or the class.

### And/Or Lesson (20 - 30 minutes)

The “do now” should give students a solid understanding of AND, and OR. Inform students that they will be using this to make different and specific regions of their canvas cause reactions. This is the starter baby step for figuring out making rectangular ‘buttons,’ which some may solidify as they move into the traffic light project.

For this code-along, be sure to explain the purpose of each expression that is written between 'and' and 'or.' This will model the thinking behind using logical operators to create buttons. Refer to the chart to show how each condition can be satisfied.

Ask students to make a copy of the And/Or Starter Code ([Trinket](https://trinket.io/python/e0b5c2fe4d)). Students will be writing conditionals to change the background color when the mouse is in each different quadrant; note that the _entire_ background will be changing, and not each individual quadrant, which can be a sticking point for students.

Begin by asking students to explore the canvas, specifically moving their mouse into each quadrant and reporting what they notice about the x and y values when they are in each area.

You will be coding along the bottom right quadrant because it is the furthest from where the mouse starts when students hit play. Ask students what they notice about values in this quadrant specifically - they should recognize that all x values are greater than 200, and all y values are also greater than 200 (the lines represent the exact centers of each axis). Together, create the following code (_**you will need to make the `bgColor` variable and use the global keyword in the draw function!**_):

```python
if mouseX > 200 and mouseY > 200:
    bgColor = color(255, 0 ,255)
```

From there, ask students to create else if conditionals for every other quadrant and an else statement to handle if the mouse is in the exact center of the screen. This can be a pair programming activity or done independently, based on the needs of your students. You can also have them complete work independently and then swap to read for comments/bugs/etc with a partner.

As students begin working, circulate to ensure:

* Commenting their code.&#x20;
* Using variables in the correct scope.&#x20;
* Using console.log() to debug and test&#x20;
* Saving their sketches with appropriate and clear titles.

### Wrap-Up (5-10 minutes)

1. Students can submit code via a Google Form if you would like to collect it. If not, have students come back together for a discussion on what struggles they encountered in this activity.&#x20;
2. Students can also lead code-alongs or walk through their code with the class.

**Guiding Questions for Assessment:**

* What is the difference between the && and || operators?&#x20;
* What was challenging about creating a hover button? Why was it challenging?&#x20;
* What was easy**?**

### Extensions

Have students create 4 rectangles in each corner of the canvas that will change a feature of an ellipse in the center of the canvas when the mouse is on top of them:

* Color&#x20;
* Size&#x20;
* X position&#x20;
* Y position
