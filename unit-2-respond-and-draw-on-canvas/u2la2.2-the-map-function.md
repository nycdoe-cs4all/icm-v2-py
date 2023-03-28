---
description: How can the map function help me control a range of values?
---

# U2LA2.2: The Map Function

### Teacher Notes and Overview

This learning activity introduces the map function and applies it to changing a sketch\`s background color to grayscale, and RGB color ranges.

This lesson is primarily a code-along, followed by oodles of student exploration via pair programming.

Make sure students enlarge their canvas - it will make the map feature way more obvious. Some students will overthink the do now - it’s really just one line of code, so encourage them to think simply if their brains start swimming in the deep end of the pool.

### Objectives

Students should be able to:

* Explain the purpose and use of the map function&#x20;
* Apply the map function within their projects

### Suggested Duration

1 period (\~45 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.7** Design or remix a program that utilizes a data structure to maintain changes to related pieces of data.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

**map**() - A built-in Processing.py function that re-maps a number from one range to another.

### Planning Notes and Materials

|                                                                                              Planning Notes                                                                                             |                                                                             Materials                                                                            |
| :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| This lesson is scheduled to take one period, but students may finish more quickly; if they do, it is meant to call back to the last learning activity. Give students as much time as they need to work! | Only a computer is required, but you may want pads of paper or other wireframing supplies to help students express their ideas if they are struggling with code. |

### Resources

* NEED PYTHON YOUTUBE VIDEO ON MAP FUNCTION
* Map Function Starter Code ([Trinket](https://trinket.io/library/trinkets/e9c1ef04d7))

### Assessments

**Formative:**

**Summative:**

### Do Now/Warm Up (5 minutes)

Change your canvas to 800x600.

In 5 minutes, create a program where the background will change as you move your mouse left and right across the screen. It should be black when you are on the left and white only when you get to the far right - in between it should be shades of grey going from dark → light.

### Vary the background with mouseX (15 - 20 minutes)

Discuss the issues that come up during the Do Now with students - they should notice that it’s black less than halfway across the canvas, which is not what we want. Prompt students to think about why this might be, by considering possible mouseX values. You can also print the text or console.log the values to show students what’s happening.

Explain to students that they probably noticed that the background is fully white before we reach that half of the screen. This is because the mouse position values range from 0 (when we are on the left edge of the canvas) to 600 (when we are on the right edge), while the background gray ranges from 0 to 255 like the rest of our colors. Our maximum `mouseX` position (600) is not the same as our maximum value for color (255), so when the mouse reaches the x position of 255 a little less than 1/3 of the way across the screen, it's already white.

This is where our map function comes in, which is a new concept for many students. Share this starter code ([Trinket](https://trinket.io/library/trinkets/e9c1ef04d7)) with students, then code along mapping mouseX from 0 to the width of the canvas, and run the program so students can see the difference. Map takes in a value, its original range, and the new range you want to _map_ those values to. Essentially, it's working to create a proportional relationship between your original range and your desired range so that everything is spaced out equally.

Your finished code should look like this (all in the draw function):

```python
bgColor = map(mouseX, 0, 800, 0, 255) 
#you can declare the variable globally (above the setup function) if it helps student understanding

background(bgColor)
```

Challenge students to determine how map could be used to make it so the canvas goes from white (on the left) to black (on the right) - allow them to work on this with their partners for \~2-4 minutes. (They should realize they will need to swap the final mapped values.)

Share out student responses (and test code as needed). Ensure students understand that this is a situation that happens over and over again as we create responsive systems: we have an input range (in this case 0 to 600), and we need to map it to a certain output range (in this case 0 to 255). It is not hard to solve this problem using simple math (a rule of three), but it is so recurrent that there is a p5 function to solve it quickly, the map function. It takes the variable to be mapped (in this case mouseX), the range that we know it will be in (0 to width), and the output range we want (0 to 255).

Once students have completed this task, draw their attention to the rest of the starter code, which has a pink rectangle and a series of challenges. Remind them that they will need to create a mapped variable for each to make it run correctly. Map can be a confusing concept for students - if they’d like to stick with individual variables that they will assign mapped values to, that is perfectly fine, however, if they would like to - or if you would like to push them to - continue using object literal, it is important to note that the mapped value would need to be assigned in draw. This is because all the values rely on mouseX/mouseY.

If students would like to pursue an object, the code would look something like this - consider showing students how to redo the bgColor code to be in a dictionary in a similar way as the following solution to the code challenge:

```python
from processing import *

def setup():
    size(500,500)

def draw():
    background(220)
    text(str(mouseX) + ", " + str(mouseY), 20, 20)
    
    rectProps = {
    "weight": map(mouseX, 0, 500, 5, 20, 
    "size":map(mouseY,0,500,75,175,
    "red": map(mouseY,0,500,0,255)
    }


    background(bgColor)
    
    
    strokeWeight(rectProps["weight"])
    fill(rectProps["red"], 0, 255)
    rect(210, 210, rectProps["size"], rectProps["size"])

    

draw = draw
run()
```

**NB:** _We are creating **everything** for this variable in the draw function because we ant the values to be constantly updating as the mouse moves!_

After another example (like showing bgColor as a property of an object, or reviewing how to set up an object for an attribute of the rectangle), give students 10 minutes to pair program or independently complete the final challenges as listed in the starter code.

### Return to Draw with Mouse (15 - 20 minutes)

Ask students to return to their drawing application and find ways they can integrate map while still drawing. **Encourage them to create an object literal to hold the properties, as this is what they’ll be working toward in the final project!**

Again, either find time to share their code or ask students to post their links for others to see.

### Wrap-Up (5 - 10 minutes)

If students post links in Google Classroom, ask students to go through and look at student projects and post comments on 3-4 of them. When posting links, you can also encourage students to post:

* Project Link&#x20;
* One thing you are really proud of&#x20;
* One struggle you had or are still having&#x20;
* Any questions or advice you would like to get.

### Extensions

Students can take each step as far as they would like, as this is solely based on exploration.
