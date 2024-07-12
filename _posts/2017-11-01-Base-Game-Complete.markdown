---
layout: post
title: "Base Game Complete!"
date: 2017-11-01 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Snake
img: snake_picture.jpg
thumb: c_thumb.jpg
published: true
---

## Almost there!

As the deadline nears snake is almost at the point I wanted it to be.

<!--more-->
-----
### How's it looking so far?

As of right now we have a working version of snake in which you go through a main menu screen into the game. As you eat food the snake grows in length as you have come to expect from snake. There is a point counter towards the top of the screen to see what size your body is currently at.

-----

Here's an example of the game playing:

[![https://gyazo.com/cecf298a99738ae95b5c170431c28a8a](https://i.gyazo.com/cecf298a99738ae95b5c170431c28a8a.gif)](https://gyazo.com/cecf298a99738ae95b5c170431c28a8a)

-----

### What's next?

Currently I am very happy with the implementation but there are also a couple of things I want to clean up. Firstly I need to add a Game Over state which changes depending on how you died, This can be done quite easily however, due to the way I've implemented the state machine. Finally there are two more features I want to add. The first one is to do with the thickness stat at the top of the screen; I plan to implement a way for the snake to grow in size width wise whilst eating. This increases the difficulty as you progress through the game as the snake begins to take up more screen real estate, leading to more risk of you crashing into your own tail. The second feature I'm going to add is a negative fruit which takes away from the snake tail and also removes some thickness.
