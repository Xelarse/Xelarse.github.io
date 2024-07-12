---
layout: post
title: "Chat functionality"
date: 2018-04-04 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Networking game
img: networkingBanner.png
thumb: networking.png
published: true
---

### Basic chat implemented

After working with the networking tutorials I aimed to get a basic chat functioning within the game.

<!--more-->
-----
#### Custom packets

After mulling over how I plan to send data between clients within the networking game I have decided to make a custom packet. This packet takes three strings as the data it stores. The first one is a type identifier. Once the packet is received it will be processed differently depending on the type. The second is the username, this is mainly used just for the chat. Finally the last string is used as the packets "data". If its a chat packet then this string is simply printed. However, if its classified as a game object then I'll parse the strings data in order to affect different game objects and their parameters.

Below is a simple template of how the packet is set up:

```C++
CustomPacket(string type, string user, string data)
{
  assign parameters to variables;
}

CustomPacket(char* data)
{
  process data back into their variables;
}

char* data()
{
  Changes current packets contents into a set of chars ready for sending.
}
```
---
#### The result!

Overall the chat is presented exactly as desired. Once the player enters the game state it creates a client component and connects to the server. The user then has to enter a username and once this is done can begin sending messages to others also connected to the server! There is a slight delay in the messages getting popped off the queue however. This was done so that the user has plenty of time to read the message before it disappears.

Below is an example of this:
[![https://gyazo.com/51116271fc6164a1b3b04074c05c8b1d](https://i.gyazo.com/51116271fc6164a1b3b04074c05c8b1d.gif)](https://gyazo.com/51116271fc6164a1b3b04074c05c8b1d)
