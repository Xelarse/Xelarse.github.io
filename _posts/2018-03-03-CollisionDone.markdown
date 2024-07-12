---
layout: post
title: "Cloud has collision!"
date: 2018-03-03 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Birdman
img: birdman.jpg
thumb: c_thumb.jpg
published: true
---

### Collision is finally implemented!

After lots of testing and messing around with code Collision is now finally implemented!

<!--more-->
-----
#### Finally got there!
After making many changes to the collision code it finally works as intended. There are a couple of rules that get checked if the player collides with an object.

Firstly what side the player collided on: This was done by checking the X - Co-ord of the player in comparison to the origin of the block in question. If the player collides on the left hand side of a block it moves the player back the xPos of the block - the players width. This way it moves the player completely out of the block. Similarly if colliding on the right side of a block it takes the xPos of the block + the blocks width and moves the player to that Co-ord in the X. Finally the top collision was done by getting the yPos of the player sprite and seeing if it was at the yPos of a block. If it was the players y_velocity is zeroed so the player stops falling and the jump bool is reset so the player can jump once again. Once the player is no longer colliding with the top of the block, y_velocity stops being zeroed so that the player can fall again.

The collisions can be seen below:

[![https://gyazo.com/c16b84a7ec20564c642f562809a772e5](https://i.gyazo.com/c16b84a7ec20564c642f562809a772e5.gif)](https://gyazo.com/c16b84a7ec20564c642f562809a772e5)
