---
description: What are the different types of data used in Python?
---

# ✨ U2LA3.1: Data Type Scavenger Hunt

### Teacher Notes and Overview

**NB:** _Students who come in with a programming background may already be familiar with different data types. In that instance, this lesson could be abbreviated, altered, or skipped._

Students have been working with data of different types all year, but they have not necessarily realized it and there has not be a solid, formal lesson on data types. This is their chance to discuss and explore the types of data being used and their purpose before they start engaging with and creating functions that will return data rather than simply performing actions on the canvas.

### Objectives

Students will be able to:

* List common datatypes used in Python&#x20;
* Test and identify the types of different pieces of data
* Recast common data types

### Suggested Duration

1 Period (\~45 minutes)

### NYS Standards

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

**Data Types**&#x20;

* **String**: characters enclosed in “ “, ‘ ‘, or \`\`.  Data can be recast as a string with the `str()` function.
* **Number**: numeric values not enclosed in “ “, ‘ ‘, or . They can be further broken down into:
  * &#x20;**integers** - positive values, negative values, and zero without decimal places. Data can be recast as an integer with the `int()` function.
  * **floats** - values with decimal places. Data can be recast as a float with the `float()` function.
* **Boolean**: a data type with only two value options often seen as “true” or “false” Data can be recast as a boolean using the `bool()` function.
* **Object**: a standalone entity, with a type and the option to have many distinct properties. A good example is a sneaker - while it may always follow the same design, it can come in different colors, sizes, types of laces, etc. This would be one object with its own properties.

### Planning Notes and Materials

|                                                                                                                                                                                Planning Notes                                                                                                                                                                               |                                                                   Materials                                                                   |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------: |
| <p>This lesson is largely driven by student exploration and it can feel as if it goes by quite quickly - however, while the actual task is brief, it is meant to lead into a discussion to deepen student understanding.</p><p></p><p>Students should be prepared to identify data types and start thinking about when data types are useful by the end of this lesson.</p> | Scavenger Hunt Starter Code and Document (_This can and perhaps should all be digital, but consider options if you think you need to print!)_ |

### Resources

* [Scavenger Hunt Worksheet](https://docs.google.com/document/d/1EybwAhYC1O6IiWEWAqvN30pXi-3Yyn-7DxMz66\_u4d0/edit) (Google Doc)
* Scavenger Hunt Starter Code ([Trinket](https://trinket.io/python/d9f2093c1e))
* NEED VIDEO ON DATA TYPES IN PYTHON

### Assessments

**Formative:**

* Exit Slip
* Data Type Scavenger Hunt Worksheet

**Summative:**

* Light Switch Project (upcoming mini project)
* Interactive Drawing Application (upcoming unit final)

### Do Now/Warm Up (2-3 minutes)

**Display on board:** Why won’t this code work?

```
ellipse(“fifty”, 100, 25, 25)
```

### Data Types Exploration (\~5 - 7 minutes)

After allowing students time to think through the do now and write down their responses, ask for some shares - many students will recognize that “fifty” is what breaks the code, despite the fact that we understand “fifty” to be a number.

Use this to launch into a conversation about data types in computer science generally, and in Python in particular. Python is less heavily typed than other languages, but it still really cares about data types and will occasionally throw up errors if we use the wrong ones, or try to combine data of different types.

Students should be familiar with:

* **Strings**
* **Numbers -** knowing that Python sees a difference between:
  * **Integers**, which are our positive/negative values and 0
  * **Floats**, which is any number with a decimal
* **Booleans** (true/false)
* **Objects**

There are actually other data types, as well, but these are the big ones that they will be encountering in the course and in their beginning journey into Python.  We are focusing on data types today because they are important when working in Python and as students continue to learn more, they will need to know how to troubleshoot and deal with many types of data.

### Data Types Scavenger Hunt (\~12 - 20 minutes)

Distribute and explain the data type sccenver hunt to students based on worksheet instructions, and then let them begin working on Part 1. The goal is for them to plug different pieces of data into the code which will then tell them the type of data the computer sees it as.

Be sure to circulate, as some students may need assistance to make sure they are removing/adding quotation marks when necessary and recording data types AND the actual data that gets printed in the correct locations.

This activity can be completed individually, in pairs, or in small groups. Best suggestion is to ask students to each complete their own activity, but compare answers within a small group.

Once the **majority** of students have finished Part 1, bring them back together briefly to complete part 2 together. Explain to students that data types matter in Python, but luckily we can _recast_ our data in different types using functions like `str()`, `int()`, and `float()`.

Slowly uncomment each line one at a time, starting with line 18. We should get this error:

_**TypeError: cannot concatenate 'str' and 'int' objects on line 18 in main.py**_

This sounds a little intimidating, but **concatenate** is just a fancy way to say 'combine.' It means our computer doesn't know how to add those two because the types don't agree. We can fix it by changing `num1` into an integer like so: `int(num1)`. This can either happen in our function, or by saving it into a separate variable:

```
#Option 1
print(int(num1) + num2)

#Option 2
num1int = int(num1)
print(num1int + num2)
```

If we then move on to uncomment line 19, we will see that despite having an integer and a float, the computer is still able to combine them. But sometimes, we may want our numbers to stay an int, such as when we are working in Processing.py. We can recast the result as an integer in one of two ways:

```
#Option 1
print(int(num2 + num3))

#Option 2
sum = int(num2 + num3)
print(sum)

```

Notice that in this instance, it works by 'chopping off' the decimal place rather than rounding in a way the students are familiar with. They can think of recasting to an int as always rounding down!

Finally, the last line should look like a familiar error - ask students how they would go about fixing it!

The big takeaway here, outside of recasting, is that students will need to use functions and be aware of how they are wrapping their values within these functions. This can take some practice, so don't worry if students are still a little unsure. They'll have a lot of chances to try again in future lessons!

### Wrap-Up (\~5 - 10 minutes)

Once students have completed their scavenger hunts, gather them to review answers - if not to all the data, to some of the trickier ones. Ask students to explain where possible and fill in any gaps or misconceptions they may have.

**Ask**:

* What are things you noticed when doing this activity?&#x20;
* Did any of the answers surprise or confuse you?&#x20;
* What happened when you tested the data type of variables?

Make sure students understand that EVERY piece of data in their code has a type, and variables simply hold onto a piece of data and take the type of that piece.

You may choose to give a prolonged exit slip where students try to determine data types without computers. Consider leveling the data so you ask questions as follows:

* What is the data type of “Rebecca”? (MILD)&#x20;
* What is the data type of 4519000? (MILD)&#x20;
* What is the data type of “Cat” != “Dog”? (MEDIUM)&#x20;
* What is the data type of \[“cs”, “is”, “the”, “best”]? (MEDIUM)&#x20;
* What is the data type of the variable mouseIsPressed? (SPICY)

For any and all, feel free to ask students for an explanation of how they know. You can choose to have students answer all questions or a mix depending on in-class performance.

### Extensions

**Ask students to dig more deeply into data.** Challenge them to try to create their own pieces of data, predict the type, and then see what comes up.

You may also want students to start understanding that the data type of **object** represents a whole set - such as an entire array - while each item in that set, or array, still maintains its own type. Consider asking them to save an array (or even an object!) to a variable and try to call individual items to see what comes up.
