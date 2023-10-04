---
description: >-
  How does code relate to real-life scenarios and social implications of
  computing?
---

# Pathfinding Algorithms and Facial Scanning

### When to Use This Extra

This lesson primarily focuses on social implications, but it does require some light understanding of code. It is best used anytime after Unit 1, when you feel your students need a brief break from writing code to instead think about it critically.

### Overview

In this lesson, students will begin by considering different algorithms for pathfinding by looking at their pseudocode and creating code summaries of these classic algorithms. They will then brainstorm what ‘cost’ could mean in a pathfinding algorithm beyond just distance and will consider technological implications to move around the city. Finally, students will rewrite the A\* Algorithm based on contemporary technological concerns.

### Objectives

Students will be able to…

* Verbalize the generalization between Dijkstra’s Algorithm and the A\* Pathfinding Algorithm
* Determine cost in a pathfinding algorithm
* Discuss how surveillance technology and other obstacles could affect the ‘cost’ of a path or route.

### Suggested Duration

\~1 - 2 Periods (45 - 90 minutes)

### NYS Standards

**9-12.IC.1** Evaluate the impact of computing technologies on equity, access, and influence in a global society.

**9-12.IC.5** Describe ways that complex computer systems can be designed for inclusivity and to mitigate unintended consequences.

\
**9-12.CT.6** Demonstrate how at least two classic algorithms work and analyze the trade-offs related to two or more algorithms for completing the same task.

### Vocabulary

* **Pathfinding Algorithms** - a method that searches a graph by starting at one vertex and exploring adjacent nodes until the destination node is reached
* **Dijkstra's Algorithm -** works by visiting vertices in the graph starting with the object’s starting point. It then repeatedly examines the closest not-yet-examined vertex, adding its vertices to the set of vertices to be examined. It expands outwards from the starting point until it reaches the goal.
* **A\* Algorithm** - combines pieces of Dijkstra's Algorithm with other pathfinding algorithms to find paths to a goal quickly and efficiently.
* **Heuristic -** a problem-solving strategy or method that is not guaranteed to find the optimal solution, but is designed to find a satisfactory solution in a reasonable amount of time

### Resources

* [Introduction to Pathfinding Algorithms](https://www.redblobgames.com/pathfinding/a-star/introduction.html) (Web Resource)
* [A\* Algorithm Pseudocode](https://en.wikipedia.org/wiki/A\*\_search\_algorithm#Pseudocode) (Wikipedia Page)
* [Introduction to A\*](https://theory.stanford.edu/\~amitp/GameProgramming/AStarComparison.html) (Web Resource)
* [Dijkstra’s Algorithm Pseudocode](https://en.wikipedia.org/wiki/Dijkstra's\_algorithm#Pseudocode) (Wikipedia Page)
* [Coding Pathfinding Algorithms](https://youtu.be/aKYlikFAV4k) (Youtube Tutorial)
  * _This p5.js tutorial is entirely optional and only if you feel working through the code of this algorithm would help you to understand it better._
* [Inside the NYPD’s Surveillance Machine](https://banthescan.amnesty.org/decode/) (Article / Web Tool)
* Reply All: The Crime Machine [Part 1](https://gimletmedia.com/shows/reply-all/76h967) | [Part 2](https://gimletmedia.com/shows/reply-all/n8hwl7/128-the-crime-machine-part-ii#episode-player) (Optional Podcast)
  * _If used as an optional extension, this would require some reflection/discussion questions to be created from the podcasts_

### Do Now/Warm Up (\~5 min)

_Display one of the maps below - it’s up to you if you want students to look at a more realistic map, or the node map. The node map will be seen again in AP CSP when talking about networks, redundancy, and fault-tolerance._

<figure><img src="../.gitbook/assets/image (18).png" alt="" width="375"><figcaption><p>Option A - <a href="https://www.teachingideas.co.uk/sites/default/files/hopevillemap_0.pdf">Kiddie Map (Full Size/Printable)</a></p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption><p>Option B - Node Map</p></figcaption></figure>

**Option A Prompt:** _How many paths can you find from Courtenay Industrial Park to a house on Queen Street?_

**Option B Prompt:** _How many paths can you find from Node A to Node H?_

### Pathfinding Algorithms

Once students have had a chance to find as many paths as possible, ask them to share out a few paths and then also ask about their strategies for finding paths.

Thinking about strategies launches them into the discussion of pathfinding algorithms, which are just the processes by which people have deduced we can find paths efficiently. Explain to students that today we will learn about two, but focus in on one.

The first pathfinding Algorithm we will discuss is Dijkstra’s algorithm. This involves assigning each piece of a route a ‘cost’ related to the distance it will take to travel, and then systematically testing every possible option and discarding the long ones until you are left with only the shortest, most efficient path. You can see this demonstrated in these two gifs:

<figure><img src="https://lh3.googleusercontent.com/voTjI_m5vJVLoFrRfMH6d7q4fbwymuLk6t8eU4krscwk3C0O99F8fbshmAFXcztA2nKwj8horqd6Yqx4FlqO9e3lbx9w1tNPs1yn5yLT2rs8JvHhqcDok6NU26ARsiO05Qf9e9QaT8NuC4TJOYv1Pw" alt=""><figcaption><p>Systematically testing every possible path and eliminating along the way.</p></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/_QSIDSZ1gmEe0XIptqcEBx5oQF8ALglZ2AQ0CVZIZ7_VeAojnGDPLXWZy5DOhvFCAjc01RUZMXUeuT_vJ3jO7PdW9L_HreBjdTF57cKLFq5qScTLNftyIJTVy1_BC2uT5h6FvpV-os8ytvWKL-TGzA" alt=""><figcaption><p>Demonstration of the ‘cost’ length</p></figcaption></figure>

It is up to you to decide how much code your students are ready for; the [wikipedia page ](https://en.wikipedia.org/wiki/Dijkstra's\_algorithm#Pseudocode)provides a great algorithm breakdown that you can turn into pseudo-code together, or you can begin by investigating their pseudocode and trying to put it into more plain English. Plan on spending \~3-5 minutes reviewing this.

Once students have at least a passing familiarity with this algorithm, explain that while it will find the shortest path, it takes quite a while since it has to check so many (especially on a large grid of notes, like the top gif). Luckily, another algorithm was developed - the **A\* Algorithm**.

The **A\* Algorithm** is only going to look at possible solutions - it won’t spend time on things that don’t actually lead to the final destination. It also uses something called a **heuristic**, which is a fancy word for an educated guess, to begin by searching with what it thinks will take the least time to get to the finish based on the starting location. This also assigns a ‘cost’ to each path based on distance, and if we want to get really nitty-gritty about it, it could be described like this:

**`f(n) = g(n) + h(n)`** → which is to say **total cost = actual cost (distance) from beginning to end + my best guess of how it will take me to get to the finish**

In practice, it looks a little like this (this gif finds two different correct solutions and then reaches a maze that has no solution):

<figure><img src="https://lh4.googleusercontent.com/JD0zjPL9urokg5qfeXEwPLqWg4hwyTp_jNjSpOL-F-9VUAVAlNH493GnyFQZTqAR8kk1mdMcQfJITvl2mKe6yZA9d4Xnmz8I9mto064CtDNMTfGpJwsxPOSQodybi3TzFAbSDkSuggY9Z6LoWLpD6g" alt=""><figcaption></figcaption></figure>

As we can see, this algorithm doesn’t need to check everything because of that heuristic - it already has a best guess of where it needs to go. From there, it checks the neighboring squares for options to continue the path, and it only explores other options when its best guess doesn’t work out as intended. Similar to Dijkstra’s algorithm, spend some time here reviewing the algorithm and/or pseudocode on Wikipedia. The goal is to get students to a place where they can summarize the purpose of these algorithms, but beyond that, you can choose to go as deep or shallow as you’d like in the experience!

### Pathfinding In Real Life

These pathfinding algorithms are a useful idea in computing; we will see something similar when learning about networks, and you might even see these things applied in maze solving or game design. But what about in the real world? We could certainly use a computer algorithm to do things like finding us a path from home to school, and it would give us the shortest distance. (If you’ve ever used Google Maps or similar, it uses a mixture of both of these algorithms to find your route!)

Because these are very abstract, generalized applications, the only cost they see are based on distance, or time, it would take to get from the start to the finish. Let’s go back to thinking about your path from home to school - there are probably many routes you could take, each with its own cost that may not have to do with distance. What are some costs that may make you prefer one route over another? Encourage students to think as outside the box as possible, and think of things that could be real or imagined to their particular conversation!

There are lots of things that may be more or less important to you as an individual, and your preferences may change over time. The world around us also changes and throws in new obstacles, some technology-driven, that we may want to be aware of when discussing cost. Let’s take, for example, facial scanning: this surveillance technology is used by police departments in and outside of New York City. [Let’s take a moment to learn about it here.](https://banthescan.amnesty.org/decode/)

_This comes direct from Amnesty International, and it may be worthwhile to do a_ [_lateral reading activity_](https://cor.stanford.edu/curriculum/collections/teaching-lateral-reading/) _on them to ensure students understand what sort of source they are engaging with!_

Have students read through the page and take a peek at some routes where facial scanning is prevalent. Ask:

* How do we feel about facial scanning, generally?
* Why might one want to avoid facial scanning, or view it as having a higher cost?
* Are there any instances where facial scanning might not affect the cost of a route?

_Allow students to drive this conversation - some students may not feel that having their face scanned is a big deal if it does not immediately change their walk, and some may struggle to emphasize or consider situations where facial scanning could be harmful. Be prepared to offer examples to help them imagine some negative scenarios._

### Collaborative Activity: Rewriting an Algorithm

Let’s take the pseudocode for the A\* Algorithm (either from the Wikipedia, or the plain-English breakdown created earlier in the lesson).  We are going to figure out and complete the following with our partners/groups (teacher’s choice!):

1. What **input** would we need from an individual to help determine the factors that change the cost of their path?
2. How can we **rewrite** this algorithm to include those costs? Is there a way that we could create pseudocode to help avoid certain high-cost factors?
3. Based on what you have learned and the Amnesty International Tool, what guidance would you want to give New York City to create more safe and efficient routes for everyone?

Ask students to take these answers and create a brief (\~5 slide) presentation that they will share with the class.

### Wrap Up

Allow students time to share their algorithm proposals and ideas, either as a gallery walk, or as quick, 3-minute presentations. Use your best judgement to determine which will be most effective for your learners!

### Extensions

This can be a great opportunity to jump off into why surveillance technology has gotten to this point and also how NYPD became accidentally reliant (and in many cases, run by) algorithms. As either homework or future class time, consider jumping into these Reply All podcast episodes:

1. [The Crime Machine Part 1](https://gimletmedia.com/shows/reply-all/76h967)
2. [The Crime Machine Part 2](https://gimletmedia.com/shows/reply-all/n8hwl7/128-the-crime-machine-part-ii#episode-player)
