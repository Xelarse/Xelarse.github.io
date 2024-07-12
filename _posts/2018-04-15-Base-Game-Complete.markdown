---
layout: post
title: "The core experience is complete!"
date: 2018-04-15 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Networking game
img: networkingBanner.png
thumb: networking.png
published: true
---

### A fair bit has changed!

It feels great to say the base game is complete, but there is lots of polish to come!

<!--more-->
-----
### What has changed since last post?
There has been quite a lot:

#### Sound effects
Since I had implemented the irrKlang sound engine early on into the project it has finally come to use. Since we are going to have multiple connected on the same host we have decided to avoid using a background track for now, but we have included sound effects on each different unit when they attack and will be adding movement sounds shortly.

#### Visual overhaul
The game has also changed a fair amount in the visual department. I personally haven't had a huge hand in the visuals but the game looks much better now and also units have an animation to signify who their attacking when they shoot.

This can be seen below:
[![https://gyazo.com/e66efbc7dbfaf3e5cb036e64231f8de5](https://i.gyazo.com/e66efbc7dbfaf3e5cb036e64231f8de5.gif)](https://gyazo.com/e66efbc7dbfaf3e5cb036e64231f8de5)

#### Reconnecting
I have also implemented a system to allow for a player to re-join a game if they disconnect or crash. Assuming that there is a game already in progress, the other play will be on a screen in which they have to wait for their opponent to reconnect. Once the player reconnects the player that is still connected will resend player id, turn and unit data to the reconnecting player in order for both games to be at the same stage. After the reconnecting player gets and processes all of the data, it sends a packet back to the server allowing the game to continue.

This can be seen below:
[![https://gyazo.com/4d05746d911b2970a9eddfcfb716a1ef](https://i.gyazo.com/4d05746d911b2970a9eddfcfb716a1ef.gif)](https://gyazo.com/4d05746d911b2970a9eddfcfb716a1ef)

---

With continued polish to the game, mainly in regards to art assets, the project is beginning to look like a very attractive vertical slice!
