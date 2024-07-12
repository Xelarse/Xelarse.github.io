---
layout: post
title: "Snake and delta time"
date: 2017-10-10 12:00:00
author: Alexander Allman
categories:
- Blog
- Code-Snippets
- Low-Level Programming
- Snake
img: snake_picture.jpg
thumb: c_thumb.jpg
---

<p>In order to make the game run smoothly on all PC's instead of basing movement off a solid amout of pixles moved and then chucking that into my update function, I have decided to impliment a delta time feature.</p>

<!--more-->
---
<p>Due my functions for movement being fairly flexible I haven't actually changed very much from last time. The main change I've made in comparison to last time was allowing the processGameActions function to have access to the GameTime class so i can get access to deltaTime, I then simply pass this through as a parameter whilst calling the functions from the snake head class in order for the class to use it to make adjustments to the posX and posY within the class based off deltaTime. I have also added a modifer so far to multiply the delta time by to increase or decrease the speed of the snake as I feel. Althought currently it doesn't actually affect the speed so I need to look into it more.</p>

## Example code

```C++
'game.cpp'
if (game_action == GameAction::MOVEHEADUP)
{
  snakeHead.moveHeadUp(float(dt.delta_time.count)));
}

'snakeHead.cpp'
void SnakeHead::moveHeadUp(float deltaTime)
{
  setSnakeHeadPosY(-deltaTime * snakeHeadMoveValue);
}
```
