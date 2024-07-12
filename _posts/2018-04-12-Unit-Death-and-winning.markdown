---
layout: post
title: "Unit death and winning"
date: 2018-04-12 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Networking game
img: networkingBanner.png
thumb: networking.png
published: true
---

### Our units can now pass

I finally implemented the ability for units to be slain in battle!

<!--more-->
-----
#### How it's done
The unit death itself is very simple, if a units squad size becomes 0 from taking too much damage then the unit gets flagged as dead and moved off screen. If all units in a team are slain then a victory screen is rendered instead, saying which player won and prompting the user to press esc to exit back to the main menu.
---
#### Here it is in action
[![https://gyazo.com/e6c3e6ebe4a5e3606122b29855c096c1](https://i.gyazo.com/e6c3e6ebe4a5e3606122b29855c096c1.gif)](https://gyazo.com/e6c3e6ebe4a5e3606122b29855c096c1)
