---
layout: post
title: "Dissecting Noughts and Crosses"
date: 2017-10-03 12:00:00
author: Alexander Allman
categories:
- Blog
- Play and Games
img: PlayAndGames.jpg
thumb: thumb01.jpg
published: true
---

## Getting into the nitty gritty

Through looking at noughts and crosses and how it's flawed at it's core we think about how we can change it up

<!--more-->
-----
### What's wrong with it?

The main issue that we come across with noughts and crosses is that once you learn the winning strategy, games either always end in a tie or a win. Due to this being the case the game stale extremely quickly which kills replayability of the game due to it no longer being entertaining.

To further analyse this in a more constructive way we used Tracy Fullerton's Play Matrix to analyse Noughts and crosses.
[![https://gyazo.com/9f111603d698ab9da821b0d6668f756d](https://i.gyazo.com/9f111603d698ab9da821b0d6668f756d.png)](https://gyazo.com/9f111603d698ab9da821b0d6668f756d)

We come to the conclusion that the game lied too heavily in the basic strategy of the game and didn't have any noise in the system so this is what we focused on.

### How did we mix it up?

Coming from the conclusion that there isn't enough chance in the system we decided to mix it up heavily by adding aspects based off a dice roll. We kept the basic rule of trying to connect 3 and dabbled with connecting 4, however, where you placed your counters relied on a d6 roll.

The first initial board we tried was a fixed distribution with a single 1 at each corner and then the two adjacent squares were 2's, the squares adjacent to the 2's were 3's and so on. We found this board reasonable because it rewarded you a lot more for rolling high on the d6 as there was a lot of 6 squares. But we also ran across the issue that we had to reroll a lot once the two 1 squares were taken for example.

[![https://gyazo.com/c553e694a7238ec8688a44a202e6e6ea](https://i.gyazo.com/c553e694a7238ec8688a44a202e6e6ea.png)](https://gyazo.com/c553e694a7238ec8688a44a202e6e6ea)

After this we tried a completely random board with no fixed distribution. This made for a longer more exciting game but could get frustrating because it was often hard to hit the win condition of connecting multiple counters together.

[![https://gyazo.com/0bbc8e9048b14ddd930e11856fa71436](https://i.gyazo.com/0bbc8e9048b14ddd930e11856fa71436.png)](https://gyazo.com/0bbc8e9048b14ddd930e11856fa71436)

Overall this was a very rewarding experience because it taught some fundamentals of breaking down a game to its core and will surely help in the future task of designing a table top game.
