---
layout: post
title: "Highscores and Wrap-up"
date: 2017-12-09 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Infinite Runner
img: runner_picture.jpg
thumb: c_thumb.jpg
published: true
---

## Highscore list

Information about setting up the highscore list and putting some finishing touches on the game.

<!--more-->
-----
### Consistent highscore list

In order to get not only a highscore, but a list that is persistent; I have used Fstream with std::sort in order to get a list that is organised in descending order.

If reading in from the highscore file. I just store the input from the file into an array, which it's elements are then rendered onto the main menu screen of the game. Once a player loses, the list is resorted into ascending order and if the score that the player has got is higher than the lowest score currently in the array, the lowest score gets overwritten, resorted and then rewritten back out to the file that is read on the game start up.

Overall this works very nicely and displays the top 5 scores gained from playing my Games

### A little extra polish

To make my game slightly more attractive and less bland I have also added a moving background into the game. This adds to the effect that you feel like you are moving and makes the game a bit more visually stimulating.

[![https://gyazo.com/2de6293c32757e5f66451907435a8d8b](https://i.gyazo.com/2de6293c32757e5f66451907435a8d8b.gif)](https://gyazo.com/2de6293c32757e5f66451907435a8d8b)
