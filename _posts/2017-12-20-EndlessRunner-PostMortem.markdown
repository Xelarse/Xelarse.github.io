---
layout: post
title: "Endless Runner Post Mortem"
date: 2017-12-20 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Infinite Runner
img: runner_picture.jpg
thumb: c_thumb.jpg
published: true
---

## Endless runner

The assignment is finally done and marked and I will be looking at some of the things I can take from this and improve in future assignments.

<!--more-->
-----
### The good
As a whole the assignment went quite well, the game worked as designed (bar a couple of things mentioned shortly) and I netted some nice compliments on my coding structure and design; which is definitely see as one of my stronger points. Even the aesthetics this time around got praised much more than snake due to the theme not being so harsh on the eyes.

The leader board system was also extremely simple but affective showing a list of high scores but could be improved upon in the future by using a STL container to a name to a score, so that the player would know who's score was who's. Also for a first attempt at procedural generation, albeit a quite simple implementation was effective in this state of the game.

---

### The Bad
Even though there were bad points within the game it's nothing to be dishearten about as they are opportunities for improvement.

One of the fairly game breaking bugs found within my game wasn't using delta time correctly. This was fine on my laptop which had vsync enabled. But as soon as it was run on the lectures laptop that didn't have it enabled, it instantly broke the game. An example of this below with vsync disabled:

[![https://gyazo.com/5d3cfd584173c4d9ecd060df34d26be1](https://i.gyazo.com/5d3cfd584173c4d9ecd060df34d26be1.gif)](https://gyazo.com/5d3cfd584173c4d9ecd060df34d26be1)

This was made even more irritating because I even had the background moving using delta time but not the actual gameplay.

The other major issue I had with my game was the way I did my jump function. It was convoluted mess with pixel perfect calculations and a timer with various states. This meant that in the future it was impossible for reuse in other projects mainly due to how specifically it was designed for this assignment. If any of my future assignments involve a jump I plan to take a similar approach to how unity has done it with a velocity based system. Here's a short snippet of how messy and inflexible the timer/jump calculation is.

```C++
if (jump_state == JumpState::TRAVELLING_UP && delta_counter > jump_delay && pos_y >= jump_peak)
{
  float pos_y_new = pos_y - travel_up_speed;
  setObjectPosY(pos_y_new);
  object_sprite->yPos(pos_y_new);
  delta_counter = 0;
  if (pos_y == jump_peak)
  {
    jump_state = JumpState::PEAK_HEIGHT;
    jump_over = false;
  }
}
```


Overall I'm quite happy with how the assignment has progressed and the final outcome bar the couple of issues that were discussed in the marking meeting. I will definitely use the mistakes I made as learning opportunities for future projects.
