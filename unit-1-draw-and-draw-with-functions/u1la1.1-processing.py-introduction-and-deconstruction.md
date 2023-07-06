---
description: How can we break down a robot into basic shapes in Processing.py?
---

# U1LA1.1: Processing.py Introduction & Deconstruction

### Teacher Notes and Overview

This lesson is an unplugged activity that has students drawing a robot using shapes and they will then use abstraction to code in your IDE of choice. It is a great way to introduce Processing.py before coding.

In this lesson, students will be introduced to the Processing.py canvas and coordinate system. It is one of the most important concepts that students will need to master in order to be successful when coding in Processing.py. This lesson is an unplugged activity in which students will draw a robot using shapes and then use abstraction decompose and code in repl.it or a local IDE. It is a great way to introduce Processing.py before coding. Students will practice abstraction (definition below) when they are decomposing the robots shapes. Abstraction is an important CS practice that is used to reduce complexity and increase efficiency.

### Objectives

**Students will be able to:**

* Create an account on [Trinket.io](https://trinket.io/)
* Explain what Processing.py is
* Describe things you can create on Processing.py
* Understand the Processing.py canvas coordinate system

### Suggested Duration

1 period (\~45 minutes)

### NYS Computing Standards

**9-12.DL.1** Type proficiently on a keyboard.&#x20;

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **Computational Media** - The practice of using programming to build expressive and interactive computer applications and media.
* Processing.py - An open-source Python version of Processing that allows people to make web pages animated and interactive.
* **IDE** - Integrated development area is a software application that provides a place for computer programmers to develop code.
* **Unplugged Activity** - an activity that can be conducted without the use of computers or electronic equipment.
* **Abstraction** - Abstraction is the process of taking away or removing characteristics from something in order to reduce it to a set of essential characteristics

**Pre-Req Vocab:**

* **Width** - Horizontal distance of a 2D shape
* **Height** - Vertical distance of a 2D shape
* **Radius** - distance from the center to edge of a circle
* **Diameter** - distance from edge to edge of a circle passing through the center point
* **Cartesian (Coordinate) Plane** - four quadrant grid with an x & y axis, origin, etc.

### Planning Notes and Materials

|                                                                                                                                                                                Planning Notes                                                                                                                                                                                |                                            Materials                                           |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------: |
| <p>This example is based off of the robot worksheet and example. If you or your class hate robots, plan on making a secondary example.</p><p></p><p>Preview shape functions - be prepared to differentiate between radius &#x26; diameter.</p><p></p><p>You’ll be using the Processing website A LOT - make sure everything linked in the lesson is unblocked and usable</p> | <p>Robot Worksheet Handout (Printed)<br><br>Pens/Pencils<br><br>Rulers<br><br>Highlighters</p> |

### Resources

* [Robot Worksheet Handout](https://drive.google.com/file/d/1CFJLhiHEBTQPxqTaNxESPxpc7F0Yto4D/preview)
* Intro to Editor && Hello Ellipse (NEED TO CREATE VIDEO)
* (Optional) [Desmos p5 Coordinate Grid Activity](https://teacher.desmos.com/activitybuilder/custom/5f73248eba4291305a86cf50)
* (Optional) [Desmos p5 Coordinate Grid Tool](https://www.desmos.com/calculator/o75y8av9jw)

**NB:** _Resources may refer to 'p5', which is the JavaScript version of the Processing library. The coordinate systems are the same, even if a few functions are a little different!_

### Assessments

**Formative:**&#x20;

* **In the Do Now:** circulate to ensure students have enrolled in course.
* **During Activity:** spot check or collect robot drawings, with special attention on finding information of shapes.
* **Wrap Up:** collect information on a post-it/notecard from the possible questions

**Summative:**

* Robot Drawing Program
* Taijitu Symbol (Upcoming Mini Project)
* Abstract Album Art (End of Unit Assessment)

### Do Now/Warm Up (\~5 min)

Have your students sign up for a [Trinket account](https://trinket.io/).

They can easily create with these options:

* Google account
* Clever account
* Email

After they’re done signing up, ask them to close their laptops or turn around with their attention to you (if in a lab).

### Intro: What is Processing? (\~10 minutes)

Start the lesson by explaining what is the main programming language of this course. After watching the video ask students the following suggested questions: [Video](http://hello.p5js.org)

**NB:** _This is made for p5, but p5 is the JavaScript version of Python. Explain to students that they have the same functionality! The video is also interactive so move the mouse around when prompted to show students how interactive p5/Processing_ _can be._

1. What did you see in the video?
2. What things do you think you can make with p5?
3. How is it similar or different to other programming languages?

Show some final project student examples to give your classroom a sense of what is possible with Processing.py. You may also need to explain to students that p5 originally existed as a JavaScript library - they, however, will be working in Python, and will be using the Python version of the same library. They can make almost all the same outputs, it will just be learning with a different language!&#x20;

* [Emoji Example](https://alpha.editor.p5js.org/SEP/sketches/HylwiSZXQ)
* [Paint Tool Example](https://alpha.editor.p5js.org/dcanizares/sketches/HklghoFlf)

### Unplugged Activity: Draw a Robot (\~10 - 15 min)

Distribute the Robot Worksheet to students and explain that p5 works on a coordinate system - it’s just a little different than the one they are used to seeing. Ask students to identify what looks different from math class, and students should notice the origin (0,0) is in the top left corner.

Explain to students that they will be creating robots on their paper using only RECTANGLES and ELLIPSES (circles/ovals). Rectangles must follow the grid-lines and ellipses must have a clear center. Inform students that they will need to find information about their shapes once they are done drawing, so be sure to follow the rules.

**During the first part:**

* Distribute Robot Worksheets and ask students to draw their robot consisting of only rectangles and ellipses
* They can use as many or as few as they want, but should try to use both shapes
* Let them draw! (Having colored drawing implements on hand can be very useful for this step)

**After the drawing**:

* Model how to deconstruct robot shapes and how to log information onto the worksheet - students need to know that the important information about an ellipse is the radius and center point, and important information about a rectangle are coordinates of the top left corner, the width, and the height. Demo as needed.
* Tell students to keep in mind the p5 coordinate system with the origin in the upper left corner.
* Ask students to work with their partners to complete the activity.
* Students will take turns “driving” (recording answers on their page based on their partner’s findings) and “navigating” (finding answers based on their partner’s drawing) until they have completed the worksheet. Students should swap after each question.

After they complete the activity, either collect the student worksheets or ask them to save it for the next lesson.

### Wrap Up (\~5 - 10 min)

End class in a way that is meaningful to you and will give you the most data on where your students are.

One option is to display the image below:

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>Sample Robot on p5.js Coordinate Plane</p></figcaption></figure>

Ask students to respond to the following questions (you may do this as a whole-class activity or as a collectible on a post-it or notecard):

* How many shapes can you identify?
* What is the location of the mouth of the robot?
* How big are the eyes?

Another option is to ask the following questions (have students answer on a half sheet of paper or index card) and collect answers as a class summary or check for understanding (you can complete on a post-it for quick collection or aloud for a discussion):

1. Share one new thing that you learned.
2. What was challenging? Why?
3. Which features would you like to add to your robot?

### Extensions

**For the Robot Itself:**\
Add a hat or another element to the robot:

1. Using rectangles and ellipses.
2. Find a partner and add one feature to their robot and have then them deconstruct the position and size of the new feature.

Have students take turns adding to their robot and identifying sizes/coordinates as needed. “Driver” adds shapes, “navigator” finds information, then switch.\
\
**For the lesson generally:**\
In this lesson or the future lessons, if you think your students need more 'at-bats' to familiarize themselves with the p5 coordinate system, consider taking an extra period to complete the Desmos activity linked under resources.
