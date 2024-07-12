---
layout: post
title: "Realm Shifter post-mortem"
date: 2018-03-08 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Birdman
img: birdman.jpg
thumb: c_thumb.jpg
published: true
---

### Realm Shifter is complete!

After finally getting the assignment marked and completed I'll look at the good and bad.

<!--more-->
-----
#### The Good stuff

Overall the assignment was a fairly good success. Not only did we manage to make a game true to our concept pitch but it was quite addictive and even though having a limited amount of levels for variation, we saw a lot of replay-ability from play testers through the idea of speed running these levels to get the lowest time possible. The switching between the different worlds worked fairly well with our implementation and in combination with my previously evolved upon state machine system the game whilst playing felt pretty complete. In our aesthetics you could clearly depict which world you were in at all times because of the very different visuals.

Below shows a gif of the finished game:
[![https://gyazo.com/fac30c977fbcce11ec91cc527eea90d2](https://i.gyazo.com/fac30c977fbcce11ec91cc527eea90d2.gif)](https://gyazo.com/fac30c977fbcce11ec91cc527eea90d2)

---
#### There is always room for improvement!

Even though the game played quite smoothly there was a lot to be left desired, especially in the refinement department.

Firstly the game itself although the aesthetics being visually different to show the difference between the two worlds it was quite jarring and quite the eyesore. Next time I would definitely use much softer colours in the dream world as the first initial switch feeling like a bad trip. This combined with the poor font choice and menu layout made it very unclear on which options changed when navigating menus. For the future a custom font that fits with the theme along side buttons for the menus are a must.

Below is an example of the unclear menus:
[![https://gyazo.com/f6b226c965f8dd596a0eca1cb1b7cc6a](https://i.gyazo.com/f6b226c965f8dd596a0eca1cb1b7cc6a.gif)](https://gyazo.com/f6b226c965f8dd596a0eca1cb1b7cc6a)


Lastly the movement of the character itself could do with improvement; Mainly when it comes to colliding with the sides of blocks mid air. The way I've coded it is so that if the player collides with the side of a block it puts them outside of the block (just in case they overlapped into it) and then changes the movement state to null, so they can't constantly bounce back into the block. This works perfectly if the player is on the ground although can be quite jarring (could be fixed with a lerp). However, whilst in the air it makes air movement very unnatural because one moment you would be moving towards a block then next movement is cancelled causing you to just fall back to the floor. A simple fix to this is to prevent the movement cancellation if the player is airborne.

Below is an example of the bug mentioned above:
[![https://gyazo.com/3b0a5fdc1e9e5b3bf0374b9b833d1e6d](https://i.gyazo.com/3b0a5fdc1e9e5b3bf0374b9b833d1e6d.gif)](https://gyazo.com/3b0a5fdc1e9e5b3bf0374b9b833d1e6d)


The movement issue could be rectified if the player just tapped the movement key again mid-air but this is initially unclear and therefore a poor implementation. In the future this could easily be avoid with some earlier play testing.
