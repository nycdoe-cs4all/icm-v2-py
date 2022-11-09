---
description: What is abstraction, and how does it relate to my code?
---

# ✨ U1LA4.1: What is Abstraction?

### Teacher Notes and Overview

**NB:** _This lesson technically covers NYS Standard **7-8.CT.4** Write a program using functions or procedures whose names or other documentation convey their purpose within the larger task. However, we know not all schools can guarantee a middle school sequence prior to this course. This lesson can be significantly abbreviated or skipped entirely based on the knowledge your students come in with!_

This lesson will serve as students’ first foray into abstraction. They will consider the hierarchy of abstraction and ponder what it means for something to be more or less abstract before coming to a formal definition as a class.

Then, they will focus on what abstractions look like in Computer Science and start thinking about the algorithms behind every day abstractions like ‘brushing your teeth’ or ‘drawing a smiley face.’

### Objectives

**Students will be able to:**

* Define abstraction&#x20;
* Create the algorithm behind a given real-world abstraction&#x20;
* Describe the abstraction that could be made for a real-world algorithm

### Suggested Duration

1 Period (\~45 minutes)

_This lesson could be extended to two class periods if you need more time or are having a rich discussion._

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.5** Modify a function or procedure in a program to perform its computation in a different way over the same inputs, while preserving the result of the overall program.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **Abstraction**: a general concept or idea, rather than something concrete or tangible. A simplified version of something technical, such as a function or an object in a program.&#x20;
* **Function**: also called procedures or methods, they are a set of instructions bundled together to achieve a specific outcome. They can be repeated to reduce redundancy and improve efficiency.&#x20;
* **Generalize**: make (something) more widespread or widely applicable.&#x20;
* **Hierarchy**: an organizational structure in which items are ranked according to levels of importance

### Planning Notes and Materials

|                                                                                                                                                                                                               Planning Notes                                                                                                                                                                                                               |                                                                                                                        Materials                                                                                                                        |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| <p>This lesson is a great chance to get students out of their desks to ponder artifacts around the room, however, if that is not feasible, you can also have students view the slides independently on a computer and discuss from there.</p><p></p><p>For portions of the lesson that may involve post-it notes, consider using a Jamboard with prompts so students can still be engaged and you can quickly gather answers and data.</p> | <p><strong>Chart paper</strong> - use to create hierarchy of abstraction posters from the virtual slides. </p><p></p><p><strong>Post-It Notes</strong> </p><p></p><p><strong>Creating Abstractions Worksheet</strong> (Digitally posted or printed)</p> |

### Resources

* [What is Abstraction?](https://docs.google.com/presentation/d/1eFb0A5CKB1SQz-Fn28MJjzE3LojV79LPJcRK0Car\_8s/preview) (Virtual Slides)&#x20;
* [Abstracting Practice](https://docs.google.com/document/d/1VpRINkLWFgT730KTnRwBK0gFdfY76GTeG31CPEjurFY/copy) (Worksheet)&#x20;
* [Abstraction - Introduction](https://www.youtube.com/watch?v=UXo7HMopEyk) (Youtube Video)

### Assessments

**Formative:**

* Post-It Check: Abstraction Definition
* Abstracting Practice Worksheet
* Exit Slip

**Summative:**

* Make an Emoji (Mini Project)
* Unit 1 Final Project (Upcoming)

### Do Now/Warm Up (2-3 minutes)

**Display on board:** What do you think it means for something to be **abstract**? Where do you see this term used most often?

### Abstraction Gallery Walk (\~5 - 10 minutes)

At teacher discretion, you may want to ask students to share their current definitions of abstraction - however, keep in mind that sometimes sharing or hearing definitions can color student’s exploration, so you may ask them to keep it to themselves and later share if their starting definition was accurate or how it changed.

If you have turned the What is Abstraction? Virtual Slides into posters, you should have hung them around the room prior to the start of class. If you are doing this as a purely virtual activity, ensure students have access to the slide deck. Explain to students that this unit is about abstraction - and we need to make sure we all understand what abstraction is. Make sure they know that abstraction shows up in many content areas and fields, and that things can be more abstract or less abstract. (It’s a scale, not a binary!)

Ask students to bring a pen and paper (notebook or post its, depending on classroom set up) with them as they partake on this gallery walk. Explain that they will be looking at every poster and jotting down things they notice and questions they have, and that when they are done, you will be asking them to revise their definition of abstraction.

Allow 5-7 minutes for the gallery walk to take place, encouraging students to spread out and take a look at every poster. Once they are done, ask them to take a seat and allow for \~2 minutes for students to revise (or double down on) their definition of abstract/abstraction.

### What is Abstraction? Mini Lesson (\~10 minutes)

Ask several students to share their definitions of abstraction and see if you can get close to a class consensus before sharing the official definition and applying abstraction directly to computer science and code. Abstractions help us to generalize processes - things that are more abstract have details removed, and things that are less abstract include more and more details.

**Note**: _In the scope of computer science, this can be present as an almost complete 180 from student understanding. When we think of programming languages, a language like Scratch would be considered more abstract because it removes so many of the code details in order to present code as blocks. A language like C++ would be considered less abstract because it includes more details that the computer needs to understand. **(Often, students see abstract things as complicated, and less abstract things as simple!)**_

Explain that one way we use abstraction in our code is **procedural abstraction**, where we take a repeated process or algorithm and give it a name so that we can constantly reuse it and not have to repeatedly type out the steps over and over and over again. (This is a good moment to ask students if they have had times in their code where they have needed to repeat lines of code they have written to get similar, but slightly altered results - many will say yes!)

Even though this seems confusing, they’ve actually been benefitting from procedural abstraction the entire time they’ve been using Processing.py. Show students this example from p5.js:

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Slide showing the definition of a p5 function and the short p5 function call side by side</p></figcaption></figure>

And explain that **line()** is an abstraction - a function! - that has been created by a programmer and included in the p5.js library. All the code on the left is the stuff you actually need to do to make a line - and because the computers have been taught that that algorithm in its entirety is a process called ‘line,’ we don’t have to type it over and over every time. We can just say **line()** and feed it numbers - inputs, or arguments - that create the line we want.

This can be 🤯mind blowing🤯 for kids, so give them some concrete examples to help them process. (Please adjust examples to fit the needs of your students!) You may ask: “What if I asked you to ‘draw a smiley face’ right now - what would you do?” Explain that **drawASmileyFace()** is an abstraction - it’s a procedure they have been taught. Hidden inside that abstraction are the steps like ‘Draw a circle for the right eye… draw a circle for the left eye about two eyes distance away…’ Write out the detailed directions for the smiley together, and explain again that you have named the abstraction and defined the algorithm needed to make the process happen. If students seem receptive, you may begin exploring the idea that you can follow these same steps with slight variations to get different smiley faces - and that would involve feeding the function different arguments that control different parts of how it is executed.

### Abstracting Practice (\~10 - 15 minutes)

Distribute the [Abstracting Practice Worksheet](https://docs.google.com/document/d/1VpRINkLWFgT730KTnRwBK0gFdfY76GTeG31CPEjurFY/copy). Based on teacher preference and student needs, this can be either as a paper copy, or a digital version distributed through a Learning Management System such as Google Classroom. Instruct students to complete the worksheet either independently or with a partner or group of peers.

Time permitting, you may choose to have students swap and compare answers or share out full class.

### Wrap-Up (\~3-5 min)

Time depending, you may choose to collect the worksheet or have students complete it for homework. Before leaving, explain to students that abstraction is a big and important concept in computer science and they are going to get lots of practice with it over the next several lessons, so if they are still processing, it’s okay!

As an exit slip, consider distributing post-its to students and ask them to self-select answer one of the following questions:

1. How has your definition of abstraction changed since the start of class?&#x20;
2. Explain how you think procedural abstraction could have been useful in a past project.&#x20;
3. Write down a question you still have about the learning today.

### Extensions

This lesson is new material for most students and involves a lot of whole-class activities, and as such, there are not many built-in extensions. If you have students who need more, consider asking them to be more detailed in their responses, or to apply more mathematical ideas to imagine what might be lurking behind p5.js functions like ellipse().
