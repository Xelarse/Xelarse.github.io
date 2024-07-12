---
layout: post
title: "The start of Snake"
date: 2017-10-09 12:00:00
author: Alexander Allman
categories:
- Blog
- Code-Snippets
- Low-Level Programming
- Snake
img: snake_picture.jpg
thumb: c_thumb.jpg
---

For our second game we have been asked to make a game based on the classic that is snake. We can switch this up the way we want to and have been given a barebones project which just includes a renderer to render a jpeg. To start learning how to use ASGE I first set my aims on simply rendering in a sprite and getting it to moved based off user input.

<!--more-->
-----
# Current implementation

For the beginning implementation of this I have made a class for the snake itself and began by focusing on just the head of the snake. Currently I have given the snake itself private floats for its X and Y position and some simple functions to change this value by 10 depending on the input pressed and then changing between states in the game.cpp

## Example

```
float snakeHeadPosY = 300.f;

void moveHeadDown()
{
  setSnakeHeadPosY(10);
}

void setSnakeHeadPosY(float yValue)
{
  snakeHeadPosY += yValue;
}
```

By adding extra states in the Actions.h file, I can chose to bind a state to a keypress and then depending on the state the game is currently in do something. So with this logic I changed between a left, right, up, down state and depending on the state called the appropriate move function. The result ended up with this!

[![https://gyazo.com/fa6daae3d2ea155009d6d2d0f58b994b](https://gyazo.com/fa6daae3d2ea155009d6d2d0f58b994b.gif)](https://gyazo.com/fa6daae3d2ea155009d6d2d0f58b994b)
