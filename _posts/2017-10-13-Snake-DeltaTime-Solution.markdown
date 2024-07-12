---
layout: post
title: "Snake and the deltaTime issue"
date: 2017-10-13 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Snake
img: snakeGameOver.jpeg
thumb: c_thumb.jpg
---

# Tackling deltaTime

So after my initial implementation of deltaTime I was extremely happy that it was all working until I discovered that changing my variable 'snakeHeadSpeed' actually didn't do anything in regards to changing the speed of the snakeHead. This left me very confused and doubting my understanding of deltaTime making me think I set it up wrong, however, this wasn't the case.

<!--more-->
-----
## Finding the problem
After clarifying my understanding of deltaTime and how it works with the system; I added breakpoints into my code where the function are called for movement to have a look through the values at this point in time. Through doing this I noticed something odd, my value for 'snakeHeadSpeed' was actually out of sync with what it's set to in the header file. Instead of updating for some reason it still held it's initial value when I made the variable for testing.

[![https://gyazo.com/9f8372e7c7d89dc42d711f4af02d7526](https://i.gyazo.com/9f8372e7c7d89dc42d711f4af02d7526.png)](https://gyazo.com/9f8372e7c7d89dc42d711f4af02d7526)

-----
## Finding the solution
Finding the solution for this one was mostly based off experience with Unreal engine over the summer. There would be various times where stuff simply didn't change when running the game even thought I blatantly changed parts of my code. This was due to me forgetting to compile my code after making changes, so I tried rebuilding the solution and voilà!

[![https://gyazo.com/e9374984d0c1c9e0154f342038e1abbe](https://i.gyazo.com/e9374984d0c1c9e0154f342038e1abbe.png)](https://gyazo.com/e9374984d0c1c9e0154f342038e1abbe)

Finally my variable has updated and is now having an effect on the snakeHead's movement speed.
