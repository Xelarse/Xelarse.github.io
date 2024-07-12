---
layout: post
title: "Jump around!"
date: 2018-02-22 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Birdman
img: birdman.jpg
thumb: c_thumb.jpg
published: true
---

## Clouds jumpin!

Learning from my past implementation in infinite runner I plan to make a much more versatile and robust jumping mechanic.

<!--more-->
-----
### Velocity is my new best friend
The mistake I made with the previous assignment was due to being pretty naïve with the idea of velocity influencing a characters movement. Since I didn't really know this existed I hard coded everything, which made the code very inflexible and have basically no reusability.

However with more experience with Rigidbodies in unity, I brought the same concept to ASGE but instead only in one axis. The was I did the implementation was instead of on the press of space my character moving up and down based of a timer; I have instead based all Y axis movement on a variable y_velocity. When pressing space this increases by a certain amount (currently 50 before tweaking). Then in the players update I move the sprite of the player in the Y axis based off this velocity, which decreases every second by gravity. Then to stop the character going through the ground I have a simple is grounded check to just reset velocity to 0 if grounded.

Here's an example of what it looks like:

[![https://gyazo.com/451a9d8ae34dd3c39e07ccac284621d0](https://i.gyazo.com/451a9d8ae34dd3c39e07ccac284621d0.gif)](https://gyazo.com/451a9d8ae34dd3c39e07ccac284621d0)

At this point collision with blocks isn't implemented just yet but now that the jump is done I can move on!
