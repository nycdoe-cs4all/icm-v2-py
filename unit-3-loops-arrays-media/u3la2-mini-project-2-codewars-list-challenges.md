---
description: How can I use lists and loops to solve code challenges?
---

# 🗃 🤓 U3LA2 Mini Project 2: CodeWars List Challenges

### Teacher Notes

This is an optional mini-project. Similar to U2LA3.3, it asks students to work on CodeWars where they will practice their coding skills on a series of challenges that focus on utilizing lists, loops, and related methods.

This lesson could, if necessary, be considered optional, as it does not build onto the p5.js library, but rather focuses on fundamental JavaScript skills in building functions with lists and loops. **Time permitting, we strongly recommend you give it a go with students to stretch their logic muscles and give them a shot at something new!**

We recommend doing a quick launch together to ensure students recall how to use CodeWars. Then, students can work with a programming partner or in small groups to complete the remaining challenges. (You may, as always, have students work independently, but that's never near as fun!)

**NB:** _As CodeWars utilizes many different programming languages, you may see them use the word 'array' in place of 'list'. While technically students are just using lists in Python - arrays have slightly different properties in this language - we should consider them interchangeable for the purpose of these exercises._

### Resources

* [U3LA2: Mini Project 2 Google Doc](https://docs.google.com/document/d/1tzrI6n9mnFhCO3yyreVvZ4IhjNR0oHiCNXm-lnjvyF8/edit)

### Launch & Prompt

To begin, review the Whole Class Example together. In this example, students are asked to sum a list and then return if the sum is odd or even. The summing is easy enough - it would look something like this:

```python
def odd_or_even(arr):
    sum = 0
    
    for num in arr:
        sum += num
```

While this helps us with the sum, we still do not know if our sum is odd or even. We can solve that with a neat little operator called a **modulo!** This may or may not be brand new to students.

An easy way to quickly teach them modulos is to tell them that a modulo - written as `%` in our code, or sometimes `MOD` in pseudocode - does a very special type of division. Ask them to look at these examples and figure out any patterns/noticings:

* 11 % 2 = 1
* 10 % 2 = 0
* 13 % 2 = 1
* 14 % 4 = 2
* 16 % 4 = 0
* 15 % 4 = 3
* 24 % 6 = 0
* 25 % 5 = 0
* 25 % 3 = 1
* 26 % 13 = 0
* 26 % 8 = 2

What they should have noticed is that a modulo is always returning the _remainder_ of a division problem.&#x20;

We can use this and what we know about even and odd numbers to help us finish our challenge. Even values are always evenly divisible by 2, while odd values will always have a remainder of 1 when divided by 2. So we could adjust our code to the following:

```python
def odd_or_even(arr):
    sum = 0
    
    for num in arr:
        sum += num
    
    if sum % 2 == 0:
        return "even"
    else:
        return "odd"
```

Remind students to use the test button in CodeWars to check themselves, then copy/paste their code over to their Google Doc before they hit submit and run the final round of tests.

Students will work in pairs or small groups to solve the remaining challenges. It is up to them to determine what level they would like to begin at - a good rule of thumb is that if they are feeling stumped, to go down a level or pop open a new tab and do a little googling.

As the teacher, you can determine parameters for grading/requirements for completion - perhaps they need to do all 3 mild and 2 medium, or 1 medium, 2 mild, 1 spicy, or some other iteration that you think would show proper mastery.

### Sample Outputs

_The best part about CodeWars is that when you complete a challenge, you can view the possible answers from people around the world! These may look more elegant than student solutions - many people who use CodeWars are college students or professionals looking to practice - but they can still be valuable for insight._

_It is strongly recommended that you work through as many of the challenges as possible yourself prior to assigning this to students so that you can help them through any sticking points._

### Extensions

While there are no planned extensions, advanced students or groups should focus on the spicy-level problems first. If they complete these quickly, there is a whole _world_ of problems on CodeWars that they should be able to keep busy with!
