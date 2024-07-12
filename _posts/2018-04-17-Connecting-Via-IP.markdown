---
layout: post
title: "Playing over two pc's"
date: 2018-04-17 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Networking game
img: networkingBanner.png
thumb: networking.png
published: true
---

### LocalWho?

Changes have been made to get rid of localhost and take ip's as a parameter.

<!--more-->
-----
#### Making extra use of the scene manager
Due to the way the I've previously set up the scene manager I have added an extra scene into the mix. This is a simple scene which takes the users input and places it into a string when you press enter. Once the user has pressed enter and this string is store it then creates the normal GameScene which now takes this IP string as a parameter on creation. Since this is the case the string is then store in the ClientComponent before the ClientComponent is actually initialised, allowing it to be initialised with the passed through IP rather than the default localhost.

Below is an example of this in action:
[![https://gyazo.com/c74a0a9dfc69bea6d1a80e8662ef913b](https://i.gyazo.com/c74a0a9dfc69bea6d1a80e8662ef913b.gif)](https://gyazo.com/c74a0a9dfc69bea6d1a80e8662ef913b)

This current implementation works across computers assuming both computers have the full project. I am currently trying to find out why the client crashes when loading in the GameScene if the client is run stand alone, away from the full project.
