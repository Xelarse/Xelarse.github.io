---
layout: post
title: "Thinking about the runner"
date: 2017-11-16 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Infinite Runner
img: runner_picture.jpg
thumb: c_thumb.jpg
published: true
---

## Can't stop won't stop

The next game on the agenda is an infinite runner in the same vein as temple run.

<!--more-->
-----
### Current thoughts for implementation

At the moment I'm leaning more towards a left to right infinite runner with similarities to the impossible game, however, unlike the impossible game it will be procedurally generated rather than being a pre-made map which ran alongside music. I also want to implement a score system with a high score table at the end for players to compare their scores to.

Through doing this I plan to adjust the window size so that it's much longer in width but the height is quite low. By doing this it will allow the player to see the upcoming dangers sooner and plan movement appropriately.

I also plan to reuse the state machine that I used in the previous game to manage inputs and generally manage the game state.

Here's a rough idea of the UML I currently have in mind:

[![https://gyazo.com/04da66b4a67b75aa7f305bf821b265ca](https://i.gyazo.com/04da66b4a67b75aa7f305bf821b265ca.png)](https://gyazo.com/04da66b4a67b75aa7f305bf821b265ca)

The idea of this is that the game has a player which generally just simply jumps, then I have multiple prefabs made that can be strung together in any order but of varying challenges. I can then randomly string these prefabs together for the player to jump and avoid.
