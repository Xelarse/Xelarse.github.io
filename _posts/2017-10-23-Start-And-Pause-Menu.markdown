---
layout: post
title: "Snake: All the Menu's"
date: 2017-10-24 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Snake
img: snake_picture.jpg
thumb: c_thumb.jpg
published: true
---
## Menu greatness

After playing a lot around with various states I can run my game in I have got a Start menu and a pause menu implemented.
<!--more-->
-----
### How It's been done

To make the menu system work in it's current state I have created a state machine which depending on that state its within, renders a different screen. This also goes deeper to have states within states to change text renderers in specific states. For example in whilst the overall state of the game is in the start menu, there are also two states which vary what text is highlighted.

-----

Below is an example of the text change when you press the arrow keys:

[![https://gyazo.com/0c27d75db64a57cda59b1fece8157546](https://i.gyazo.com/0c27d75db64a57cda59b1fece8157546.gif)](https://gyazo.com/0c27d75db64a57cda59b1fece8157546)

Below is an example of the whole menu system changing from the Start menu state to game state and then into pause state:

[![https://gyazo.com/ed3c0abf2d96daf3a27eddf72f317e0d](https://i.gyazo.com/ed3c0abf2d96daf3a27eddf72f317e0d.gif)](https://gyazo.com/ed3c0abf2d96daf3a27eddf72f317e0d)

-----
### Issues with this implementation

The current issue with the system I have implemented is that currently is that most if not all the state management is within the game class itself and is bogging down the input and processGameActions functions which is making them extremely hard to read briefly and to an outsider would look like a complete mess. To solve this I plan to abstract the state machine itself into it's own class. By doing this I can call various functions to check states and have the inputs passed into the state machine to change states, rather than all of this being within the input function itself. Decoupling this would make my code much more legible in the long run and allow the input function to only handle inputs.
