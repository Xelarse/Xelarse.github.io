---
layout: post
title: "Object pool for blocks"
date: 2018-02-19 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Birdman
img: birdman.jpg
thumb: c_thumb.jpg
published: true
---

## With varying scope comes lots of de-allocations
Time to fix it with an object pool!
<!--more-->
-----
### Object pool
Whilst using unique pointers in this assignment I was noticing things falling out of scope frequently and getting de-allocated. This is good because it shows that the unique pointers are working and stopping memory leaks, however, it's extremely irritating when trying to render scenes and objects suddenly don't exist after initialisation.

In order to tackle this problem I created an object pool for blocks. The core concept is pretty simple, once you create an block pool there are two vectors at size 50 containing the two types of blocks used in the game. These blocks have a bool to show whether or not they are being used. If the user wants to get a block object from the pool a function call is made and it searches for the first block in the pool that isn't being used and hands back the raw pointer to said block.

Below is a screen shot of the header of the class:
[![https://gyazo.com/ef3bda948fa6c4ef0b6e4da76c8d1de9](https://i.gyazo.com/ef3bda948fa6c4ef0b6e4da76c8d1de9.png)](https://gyazo.com/ef3bda948fa6c4ef0b6e4da76c8d1de9)
