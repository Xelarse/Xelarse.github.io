---
layout: post
title: "Gathering Storm Post Mortem"
date: 2018-04-22 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Networking game
img: networkingBanner.png
thumb: networking.png
published: true
---

### Networking game is done!

As the dust settles our final project has been handed in and a bit of reflection is due.

<!--more-->
-----
#### How did it go?
All in all I've been pretty happy with how the game has turned out. Through playing it feels quite natural to move units and going through the various menu scenes. This was mainly due to learning how to use more input handlers than just the keyboard as the game now has mouse inputs and even just small attention to details such as hovering over buttons makes the whole experience feel much more intuitive.

The buttons can be seen below:
[![https://gyazo.com/214888910f6a0ef8df67e78ac708341c](https://i.gyazo.com/214888910f6a0ef8df67e78ac708341c.gif)](https://gyazo.com/214888910f6a0ef8df67e78ac708341c)


#### What could go better next time?
As always with post mortems there are plenty of things that need improving or refining so that things run smoother the next time. This is especially true with this project due to the more complex systems of having a game multi-threaded and also managing network data.

The biggest thing that I was unhappy with how a lot of our codebase was laid out. Even though units could be changed in a JSON file and didn't require rebuilding, if you wanted to add new units or change the names of existing ones then much of our game would break. This was due to the units moving and attacking being hard coded and being dependant on the name of the unit itself. In Future versions I would definitely engineer a solution so that new units can be added, removed and changed at will without breaking the rest of the code.
  Much of the codebase in addition to this could have been abstracted out of the main game scene. For example we should've abstracted the game board and much of the movement and attack queries into their own abstracted class. This would've split up the codebase into a much more legible and organised manner as currently all of the game logic bar collision logic is stored in the main game scene; making it ~1100 lines in length.

As for the networking I was pretty happy how well it worked but it also was fairly restrictive. For future implementations I want to learn how to use templates to use custom operators to feed information into and out of packets. This would allow for a much easier understanding of packet processing and allow for much more flexible data transmission overall, as currently our packets only take three strings. Which are packet type, username and data respectively.


#### It all sounds so doom and gloom
Overall considering the circumstances I am extremely happy with how the game plays and also how it looks. Especially considering this was a project that was assigned to four people but only myself and one other group member actually attributed to it. Over the summer in my free time I plan to remake the game with a much better structured approach which is based around the networking, as opposed to the networking fitting the game. This is mainly because I find the whole networking component of a game fascinating and by using C++ you can really manipulate the data you want to send in which ever way you may personally want to.
