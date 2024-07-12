---
layout: post
title: "The Changes Fruit Can Make"
date: 2017-10-31 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Snake
img: snake_picture.jpg
thumb: c_thumb.jpg
published: true
---

## Inheritance Mixup!

Whilst looking at implementing my fruit to grow my snake I've realised my structure of my code could do with a bit of an overhaul.
<!--more-->

### Fixing a bit of a mess

Due to starting my project with not as much planning I should've done in order to try to learn the new engine. My classes have not been linked as clearly as they should be and obvious links have been completely missed. For example at the beginning I had a "Snake Head" had a bunch of "Snake Bodies". This in essence was a good idea but through both of them using very similar functions and now wanting to also implement fruit into the mix, instead of adding fruit into its own class with very similar functions; I reworked my classes to inherit from a "GameObject" class.

-----

Previously I had this structure where in this case the snake head and body shared many similar variables such as position, a renderer and an update.

[![https://gyazo.com/ea51989a4291eafad0541abde646b9ed](https://i.gyazo.com/ea51989a4291eafad0541abde646b9ed.png)](https://gyazo.com/ea51989a4291eafad0541abde646b9ed)

Through doing the setup below I have been able to not only been able to use the GameObject class to store any common variables and functions between objects in my game.


[![https://gyazo.com/5d174629d4901c36a8c9e48feef64dc9](https://i.gyazo.com/5d174629d4901c36a8c9e48feef64dc9.png)](https://gyazo.com/5d174629d4901c36a8c9e48feef64dc9)


 I have also allowed for greater expansion later on, this is the case because when checking for collision of sprites I can have the GameObject have a sprite member in the protected section of the class in which the offspring can inherit and use; but when checking for the actual collision I can pass through any game objects and have their collision checked rather than making a custom made function just for the snake head and fruit. By doing this it will also allow me to make easy collision checks with the body as well.
