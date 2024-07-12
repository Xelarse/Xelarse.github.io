---
layout: post
title: "Runner Progress update"
date: 2017-11-18 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Infinite Runner
img: runner_picture.jpg
thumb: c_thumb.jpg
published: true
---

## We have a jumping block!

Just a quick update on how the infinite runner is looking so far

<!--more-->
-----
### implementation to date

As of this blog post I currently have a jump linked into my state machine so that I can get the block to jump up and come back down after a jump. I did this by using a fairly simple timer that's linked into the update function as an example of how it currently works:

```C++
if(timer > 1)
{
  "logic here"
  timer = 0;
}

else
{
  timer += delta_time;
}
```

By using this it allows for a delay for logic in the program without actually stalling the program for this delay, I used a similar timer function in my snake for movement.

An example of the jump can be seen here:

[![https://gyazo.com/e1367a544b36f7d397f419b9798ae21e](https://i.gyazo.com/e1367a544b36f7d397f419b9798ae21e.gif)](https://gyazo.com/e1367a544b36f7d397f419b9798ae21e)

I have also changed how I decided to set up the various types of blocks in the game. In essence from the only real difference from UML in the previous post is that I've removed the spike class entirely and now use a bool to decide on which block spawns and whether its a in essence one you can land on or one that will kill you if you touch it.

For example if the bool is set to false this safer block will spawn:

[![https://gyazo.com/6570dd0401b2dbe082f55d869cb1b649](https://i.gyazo.com/6570dd0401b2dbe082f55d869cb1b649.png)](https://gyazo.com/6570dd0401b2dbe082f55d869cb1b649)

And if the bool is set to true then a more evil block will spawn:

[![https://gyazo.com/90e6e03f7ec1565694b680fbc8a7e189](https://i.gyazo.com/90e6e03f7ec1565694b680fbc8a7e189.png)](https://gyazo.com/90e6e03f7ec1565694b680fbc8a7e189)
