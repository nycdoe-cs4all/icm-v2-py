---
description: How can I utilize the pixel values on a canvas to create interactive work?
---

# Playing with Pixels

### When to Use This Extra

This lesson requires students to have a solid understanding of dictionaries, for loops, and how to import images into their program.

* **Earliest/Natural Flow:** Anytime after lesson **U3LA3.1 Loading Images.** At this point, students will have covered all things they need to be successful in this lesson.
* **Natural Flow:** This lesson is a great inclusion as a part of Unit 5, possibly before students move into their final projects.

### Overview

This lesson is primarily a tutorial as it involves several new skills and a lot of moving pieces. Once the tutorial is complete, the student challenge comes in the form of a mini project where they are asked to apply the skills they learned in a creative way to create something new. Please be prepared for a longer-than-normal code along and make sure your students are ready for that, as well!

### Objectives

Students will be able to:

* Load pixels from a canvas
* Save pixel data into a usable dictionary
* Utilize pixel data to create designs in their programs

### Suggested Duration

\~2 - 3 Days (\~45 - 135 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.7** Design or remix a program that utilizes a data structure to maintain changes to related pieces of data.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **pixel -** a minute area of [illumination](https://www.google.com/search?sca\_esv=570966760\&rlz=1C5GCEM\_en\&sxsrf=AM9HkKkGzf9\_5xNa9I8naIaFZCLp271oGg:1696515853821\&q=illumination\&si=ALGXSlb91IXEiYApD91csfAulari\_bO0BSo1Plg\_iuFefmHS8p1LSkeeo4MTEV90lL\_5OA0ybsVot2EpXR99T9IU\_dF9TSlOd27V7OdDatv3ngVx3Bh5Ucc%3D\&expnd=1) on a display screen, one of many from which an image is composed.
* **`loadPixels()` -** a function that will load color values for every pixel currently a part of the canvas into an array called `pixels`.
* **`get()` -** will take specific values from the `pixels` array. (Can also be used to get other data, but that is how we will see it in this lesson!)

### Resources

* [Completed Sample Code](https://trinket.io/library/trinkets/77efdcb7d6) (Trinket)
* [loadPixels()](https://py.processing.org/reference/loadPixels.html) and [get()](https://py.processing.org/reference/PVector\_get.html) (Processing.py Reference Sheet)
* [Starter Code](https://trinket.io/library/trinkets/778838ecbd) (Trinket)

### Do Now/Warm Up (\~3-5 minutes)

When we give shapes a size in Processing.py, what unit are we measuring in? What do you think the size of that unit is?

### Exploring and Capturing Pixels (15 minutes)

Begin by explaining the do now - the units they are measuring in are actually _pixels_. Each pixel is a tiny area of illumination on the screen - really just a dot! (If students have ever adjusted screen settings, they may have noticed they'll be listed in DPI or PPI - literally dots per inch or pixels per inch.)\
\
Everything they see on a screen is just made up of pixels, and they have been controlling the appearance of those pixels in their Proecessing.py sketches. In addition to telling the pixels how to look, we can also load all the pixel data of a project and use that to make some cool interactive projects - including hidden images, which is what we will explore together today!

To begin, we will make a copy of the [Starter Code](https://trinket.io/library/trinkets/778838ecbd). Notice that there isn't much there - in setup, we setup two variables, and we load an image into one. We haven't done anything else yet, though!

**NB:** _This starter code is fairly basic - if you would prefer, you can have students begin with a blank canvas to practice loading images, or you can create your own version with an image other than the default puppy one._

Our first goals are to display our image on the screen, load the pixels from the image into a saved data structure, and then get the pixel color data to be a little more organized.

Let's start by displaying our image on the screen:

```python
from processing import *
from collide2d import *

def setup():
    size(500, 500)
    global img, pDictionary
    img = loadImage("puppy.png")
    
    image(img, 0, 0) #display image, top left corner of image matches top left corner of canvas
    
    
    #background(220) # cover image

def draw():

    
    
draw = draw
run()
```

Easy enough, right? Now let's load in our pixels. For our purposes, these code blocks will _only show the setup() function -_ please know the other parts are still there, we are just trying to focus in!

<pre class="language-python"><code class="lang-python"><strong>def setup():
</strong>    size(500, 500)
    global img, pDictionary
    img = loadImage("puppy.png")
    
    image(img, 0, 0) #display image, top left corner of image matches top left corner of canvas
    loadPixels() #load all pixels of current screen - creates array called pixels
    
    #background(220) # cover image
</code></pre>

This is also an easy, one-line step! Now part of the magic of the loadPixels() function is it automatically populates a system variable called `pixels` with an array of all the color values of the pixels. We can test it by writing under `loadPixels()` a statement like `print(pixels)`. You'll notice the output looks CRAZY! That's because these numbers all represent color values, but in the raw way that makes sense to the computer and may be difficult for us to parse. (Feel free to comment out the print statement immediately so you don't have to stare at silliness!)

It's also worth noting that this list has saved pixels left to right, top to bottom, but that means it's not _super_ readable for us. The color saved at index position 0 in the array is the color for the pixel at coordinate (0,0), for example, and the color saved at index position 1 of the array is the color for the pixel at coordinate (0,1). This might be useable if we had a small image, but on a 500 by 500 canvas, there are _250,000 pixels!_ That's a lot of information!

Because of this, we are going to create a dictionary that will start empty and we will populate using some for loops. To create the dictionary, we would do something like this (we are grouping our variables for organizational purposes, which is why the line order may seem off to you):

```python
def setup():
    size(500, 500)
    global img, pDictionary
    img = loadImage("puppy.png")
    pDictionary = {} #create dictionary to organize pixels
    
    image(img, 0, 0) #display image, top left corner of image matches top left corner of canvas
    loadPixels() #load all pixels of current screen - creates array called pixels
    
    #background(220) # cover image
```

Now, to get data into that dictionary, we need to loop through every possible x value and every possible y value in our canvas. For each one, we want to create a new dictionary key that is easy for us to read - let's say it'll look something like `'x,y'` with appropriate values filled in - and use that key to save the color value in a dictionary.  For this, we will use the `get()` function, which is part of Processing.py and will automatically access the `pixels` list to find our color information at the appropriate coordinate.

We can use this process and check it by printing the value of `pDictionary` once we finish:

```python
def setup():
    size(500, 500)
    global img, pDictionary
    img = loadImage("puppy.png")
    
    image(img, 0, 0) #display image, top left corner of image matches top left corner of canvas
    loadPixels() #load all pixels of current screen - creates array called pixels
    
    for x in range(width): #loop through every x
        for y in range(height): #loop through every y with every x
            newKey = str(x) + "," + str(y) #save string "x,y" to create dictionary key name
            pDictionary[newKey] = get(x, y) #for every newKey, get the color value from pixels and save it to dictionary
    print(pDictionary) #comment out once you've tested this!
    
    #background(220) # cover image
```

So now we have a super useful dictionary, but nothing is really going on in our program. We are going to make the actual activity happen in `draw()`! We only have one last thing to do here, which is to comment the `#background(220)` on the last line of `setup()` back in. This will cover the image, and this is what we want for what we will do next.

### Drawing with Pixels - Hidden Images (\~10 - 15 minutes)

Now in part 2, we are going to take all that good, juicy data we setup for ourselves and use it to create a program that will slowly reveal a hidden image in a cool, watercolor-esque style.

To do this, we are going to need to use our `pDictionary` in the program. Please note that in this section, the lesson will _only be showing code from the `draw()` function!_ The rest is still there, we are just focusing in to avoid confusion.

```python
def draw():
    global pDictionary #make coordinate:pixelColor dictionary accessible
    
    
draw = draw
run()
```

To reveal our hidden image, we want to be able to take the current position of the mouse, use it to retrieve the correct color, and then draw an ellipse (really, a circle) on the screen with the correctly colored pixel for where our mouse is based on the image below it.

First, we need to know where the mouse is, which we know we can use `mouseX` and `mouseY` for. We also want to save that as a readable key for our dictionary, which is easy as we did something similar in `setup()` - but we have one spanner in the works: our mouseX and mouseY sometimes return _decimal_ values, which won't match any of our dictionary keys. We can solve that by first rounding them with the `int()` function, then turning them to strings to create our key. The process would look like this:

```python
def draw():
    global pDictionary #make coordinate:pixelColor dictionary accessible
    
    currentLocation = str(int(mouseX)) + "," + str(int(mouseY))
    
draw = draw
run()
```

Now, let's put that to use!

```python
def draw():
    global pDictionary #make coordinate:pixelColor dictionary accessible
    
    currentLocation = str(int(mouseX)) + "," + str(int(mouseY))
    fill(pDictionary[currentLocation]) #use mouse location to get correct pixel color for ellipse
    ellipse(mouseX, mouseY, 10, 10)
    
draw = draw
run()
```

If we play our program and move our mouse around the screen, we should see colored dots appearing, and we may even start to see the image coming through if we make a lot of them! We do have a few issues that we can sort out.

First, most importantly, you may notice that if you move the mouse _below_ the bounds of the canvas it throws an error. This is something to do with how the display area below the canvas is read. We can fix it by just putting our previous code into a conditional so that the drawing only happens if we are above the bottom of the canvas:

```python
def draw():
    global pDictionary #make coordinate:pixelColor dictionary accessible
    
    if mouseY < height:
        currentLocation = str(int(mouseX)) + "," + str(int(mouseY))
        fill(pDictionary[currentLocation]) #use mouse location to get correct pixel color for ellipse
        ellipse(mouseX, mouseY, 10, 10)
    
draw = draw
run()
```

Our second issues is that our ellipse may look a little sad given it has a solid black stroke around the outside, and with one uniform size of 10, it may be obnoxious to try to fill our whole shape. So let's fix both!

```python
def draw():
    global pDictionary #make coordinate:pixelColor dictionary accessible
    circSize = int(random(1, 15)) #set random size for ellipse - grouped at top for organization of variables
    
    if mouseY < height:
        currentLocation = str(int(mouseX)) + "," + str(int(mouseY))
        fill(pDictionary[currentLocation]) #use mouse location to get correct pixel color for ellipse
        noStroke() #turn off stroke for design purposes
        ellipse(mouseX, mouseY, circSize, circSize)
    
draw = draw
run()
```

And tah-dah! Just like that, you have created a hidden image program.

### Utilizing Hidden Images (30 - 60+ min)

It's now going to be your turn to create something with a hidden image by recreating the same steps we learned here! Your goal should be to create a program with hidden images (created in setup) and always visible images (created in draw).&#x20;

Anything made in `setup` will only be created once, at the beginning of the program, and when you use `loadPixels()` it will capture _everything on the screen in setup._ You can include multiple loaded images or even designs that you draw with Processing.py shapes.

Anything made in `draw` will be drawn in the repeated loop of the draw function, meaning it will be always visible on the screen and cannot be drawn over.

Get as creative as you can!

### Wrap Up (\~5 - 15 minutes)

Depending on the dedication you give to this project, you may have students just submit their work, or do some sort of gallery walk or presentation so that they can show off what they made to other people in the room.

### Extensions

Look for an application of this that is more than just aesthetic! You could create a game like [Hocus Focus](https://www.hocusfocus.fun/?reddit), which has a hidden image and a bullseye drawn on top of it. In this game, as you move the mouse the size of the rectangles you draw gets smaller and smaller so the image comes more and more into focus until you can find and click the rectangle.

If students are feeling adventurous, there is a function called `updatePixels()` which will update the values in the `pixels` array (which would likely necessitate repeating the steps in `setup()` to be useful to students) - they could explore this as an option after making changes to the program, for example, and it may give some students ideas of new ways to engage with their program.
