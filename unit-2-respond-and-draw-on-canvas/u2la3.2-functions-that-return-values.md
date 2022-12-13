---
description: How can I write functions that take in numeric inputs and return a value?
---

# ✨ U2LA3.2: Functions that Return Values

### Teacher Notes and Overview

**NB:** _This lesson technically covers NYS Standard **7-8.CT.4** Write a program using functions or procedures whose names or other documentation convey their purpose within the larger task. However, we know not all schools can guarantee a middle school sequence prior to this course. This lesson can be significantly abbreviated or skipped entirely based on the knowledge your students come in with!_

This lesson will allow students to get practice looking at functions that take in values and return a value, specifically focusing on numbers. This is a little bit of a “method to the madness” lesson as they will start by looking at reading nonsense examples before they begin writing their own for given prompts in the next lesson.

This is a great AP CSP preview lesson, as reading this sort of pseudocode is a part of the AP Exam!

Please remember that reading and writing code are separate but related skills, much as reading and writing in English are separate but related skills. This will ask students to practice the former which may feel unfamiliar and silly to them, but that’s okay - it will make them better computer scientists in the long run!

### Objectives

Students will be able to:

* Read pseudocode functions to determine their output

### Suggested Duration

45 - 90 minutes (1-2 class periods, depending on the amount of time you would like to devote to practice.)

It’s recommended you spend more time on practice if you know that many of your students are planning to continue to AP CSP.

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.5** Modify a function or procedure in a program to perform its computation in a different way over the same inputs, while preserving the result of the overall program.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

_**Review:**_

* Output/Return
* Input&#x20;
* Argument&#x20;
* Parameter&#x20;
* Function/Procedure

### Planning Notes and Materials

|                                                                                                                                                                                                                                                                                                                                                                                                                                  Planning Notes                                                                                                                                                                                                                                                                                                                                                                                                                                  |                                                                                                                        Materials                                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| <p><strong>The start of this activity is physical and interactive and requires some prep work!</strong> Make sure you have cut out the algorithm cards and stacked them in a safe place in your room. You may want to leave post-its, a pen, and a calculator next to them to help students in recording their answer.</p><p></p><p><strong>This lesson also involves standing in the hallway and moving in and out of the classroom - warn your neighbor teachers beforehand!</strong></p><p></p><p>Students will be acting as the function inputs, so you will also need them to know which input they are, and which value they are. The numbers are completely up to you, but please make sure they are prepared in advance!</p><p>Additionally, the extra practice in this activity comes from DeltaMath - if you do not have a DeltaMath account, consider making one.</p> | <p>Printed algorithm cards </p><p>Papers with numbers (large, written dark) </p><p>12 papers: 3 labeled a, 3 labeled b, 3 labeled c, each with a number </p><p>Markers </p><p>Post-Its </p><p>Calculator </p><p>Computers </p><p>DeltaMath Account</p> |

### Resources

* [Algorithm Cards](https://docs.google.com/presentation/d/1lNv8WDCP4hB40Xhh6qL0UiFRe298AiZsYPrtlbKX6-Q/copy) - print and cut out for student use
* [DeltaMath.com](https://www.deltamath.com/)
* [Functions that Return Values](https://youtu.be/qRnUBiTJ66Y) (Youtube Video)

### Assessments

**Formative:**

* Exit Slip (formative)
* DeltaMath Assignment (formative)&#x20;

**Summative:**

* Light Switch Game (Upcoming Mini Project)
* Interactive Drawing Application (Upcoming Unit Final)

### Do Now/Warm Up (\~2 - 3 minutes)

**Display on board:** What is an input? What is an output? What do you think it means to return a value?

_As class is starting, be sure to have a small function area set up for your student inputs. You will need to have the algorithm cards, stacked, along with a post it and pen (optional for students to calculate values), and calculator. You may want to mark or label the area. Take the a/b/c papers with the numbers on them with you!_

### Returning Values Activity (15 - 20 minutes)

Discuss the definitions to input and output with the students, and explain that an output is what a function is returning back to the program. Explain that today you are going to explore functions that return a value to a program, and you are going to do that by using the classroom as an example.

Ask everyone to stand up and go out into the hallway. (As an alternative, you could do this with different sections of the room and having a secret function corner, but it’s not as impactful.) Once you’re in the hall (or moved away from the secret corner) explain that the classroom represents **an empty function**. Right now, it has no inputs, no definition - the steps that are being followed - and no return value. But it will shortly!

**FUNCTION ONE: NO RETURN VALUE** Tell students that there is now a rule defined in the function, and to make it work, we need three inputs - which will be students! Give one student one of the a’s, another one of the b’s, and another one of the c’s. Direct them where to go to get the rule and explain that they need to work as a group to follow all the directions and then come back out and report their findings.

Allow students into the room to find the rule while you wait with the rest of the group. When the group emerges, ask them what information they are returning ot the class. They should not have anything ot return. Ask them if they followed any steps, like doing a math problem - they should say yes. Explain to students not in the room that their function suffered from not returning a value - so while something happened in the room, it’s a secret to everyone standing outside. Make sure to take the old paper from the returning students to ensure it is set up for the next round.

**FUNCTION TWO: RETURN A VALUE** Select three more students and give them each an a/b/c with number paper. Send them into the room to complete the next function, which now has a return value. When they come out, ask them what they are returning to the class. They should be able to give you a value. Explain to the class that somewhere in the rules of this function, the students were told to give this value back to the rest of the program, which is why we have a number now when we didn’t before.

Ask the students how they arrived - they will not state the rule. Explain to everyone else that usually, functions are defined to the program, but the details are hidden from the user (which in this case is the class). This is what we mean when we say functions are an abstraction, or that we have removed unnecessary details. You’re welcome to allow some students to guess what the rule might be, but that’s not the purpose of the activity. Tell students you’ll test this algorithm another time with three more values, so anyone with guesses can test it again.

**FUNCTION TWO: AGAIN!** Send in another a/b/c to test the same algorithm a second time, with new values. Follow the steps of coming out and reporting - things should move more quickly now.

**FUNCTION THREE:** More Return Values Send the final group in to deal with one new function and return the value. Explain to students again that this function has inputs, a definition, and is returning a value - even though the definition is a secret to us now if we were the programmer, we would be the ones deciding how it runs and writing it behind the scenes, and then we could use it again and again with any inputs that we want.

### Reading Functions Lesson (\~10 minutes)

Explain to students that you are going to practice the idea of defining functions and calling them with different inputs to see what is returned altogether. You will start by looking in a Python format, but eventually, the practice will be in **pseudocode** which is similar.

<figure><img src="../.gitbook/assets/Screen Shot 2022-12-13 at 2.12.11 PM.png" alt=""><figcaption><p>Side by side comparison of a mystery function in Python and DeltaMath</p></figcaption></figure>

Display both and explain the similarities and differences as you walk through how to read the code and how to map out their thinking to determine an answer. Here, we would see that a = 5, b = 6, and c = -4, so when we substitute, we would be returning 6 - 5 - -4 which gets saved to the variable `ans`. When we `print(ans)`/`DISPLAY(ans)` we thus end up with an answer of 3.

After going through one as a class, ask students to attempt the following independently. **You may wish to give this question as a post-it note check so you can collect student answers and group for remediation as students move into independent practice on DeltaMath.**

<figure><img src="../.gitbook/assets/Screen Shot 2022-12-13 at 2.11.20 PM.png" alt=""><figcaption><p>Side by side comparison of a mystery function in Python and DeltaMath</p></figcaption></figure>

Students should arrive at an answer of -19. Ask a student to step through their process and correct any errors or misconceptions, or group students based on understanding to remediate during independent practice.

Explain that in the practice, students will only be seeing the pseudocode example, but once they begin writing their own code, they will be following Python syntax. Make sure they understand that the logic behind the inputs and output/return is the same in any language, and even though these are nonsense functions, being able to read and understand them will be helpful once they have functions with a purpose to read/write.

### Reading Functions Practice (\~10 - 45 minutes)

**NB**: _Prior to the lesson, you should have a DeltaMath account and have created an assignment for your class. The skills you are using are under **Pseudocode Exercises**. Specifically, focus on Procedures and Parameters (Level 1) and if you’d like, (Level 2). If you are practicing for an entire period, consider setting a practice that is 10 Lv 1 questions, 5 Lv 2, and 3 Lv 3. You can adjust values to meet the needs and time constraints of your class._

Allow students to work independently while you circulate. Note that if you need to pull students for remediation, you can pull up DeltaMath on your computer to display a sample problem and have an entire group work off of the same one (as opposed to being served random problems when they work on their own).

### Wrap-Up (\~5 minutes)

At the end of the practice (for whatever amount of time you have deemed correct for your classroom), consider giving students an exit slip to measure where they are at with this concept. You may choose to go one of two ways:

#### **Option 1:**

* Generate a Level 1 and Level 2 (and possibly even Level 3) problem from DeltaMath, print on a paper or distribute digitally, and ask students to choose one to answer.

#### Option 2:

Ask students to choose one of the following questions to answer:

* What is something you learned about functions that return values during this lesson?&#x20;
* What is something that still confuses you about functions that return values?&#x20;
* What are you curious about in using functions that return values?

### Extensions

**This lesson easily scales - just give students more difficult procedures to read!** Enjoy!
