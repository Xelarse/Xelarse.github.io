---
layout: post
title: "Network movement!"
date: 2018-04-11 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Networking game
img: networkingBanner.png
thumb: networking.png
published: true
---

### We now have movement over the network!

After adding some extra unpacking logic to the client we now have unit movement!

<!--more-->
-----
#### How it's processed
In order to send the units data by using the custom packet I made, I use the initial string as an identifier and the final string as the data holder. So when the client receives a packet that is of type unit, the packet gets moved into a unit processing queue in which the final string is broken up into: which unit it's affecting, their position on the board and the units hp and squad size. This is done through using an "&" between each value as a delimiter.
---
#### How it's sent
Sending the packets themselves is much simpler. Once a unit has either been damaged or position has been changed they get flagged as being changed. When the player ends their turn all units that have been changed during their turn get put into a packet and once all have been send an end turn packet also gets sent. This allows the other client to know once they have received all the unit updates required.
---
#### Here it is in action
[![https://gyazo.com/fa0c3018005815f413797cee7fef4995](https://i.gyazo.com/fa0c3018005815f413797cee7fef4995.gif)](https://gyazo.com/fa0c3018005815f413797cee7fef4995)
