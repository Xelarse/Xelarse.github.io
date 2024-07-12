---
layout: post
title: "Sygenta Farming Game Post Mortem"
date: 2019-03-14 12:00:00
author: Alexander Allman
categories:
- Blog
- Internship
- Mobile Pie
img: syngentaBanner.png
thumb: syngentaWheat.png
published: true
gameCarousel:
    urls:
    - "/assets/carouselImages/syngentaPostMortem/game/commandSelect.gif"
    - "/assets/carouselImages/syngentaPostMortem/game/removeCommands.gif"
    - "/assets/carouselImages/syngentaPostMortem/game/play.gif"
    captions:
    - "Add commands using the toolbox on the left"
    - "Remove single commands with 'X' or the whole row with the trash can"
    - "Press the play button to see where your tractor goes based off your commands"
---

### Educating the masses on farming technology

For a smaller task in between my larger project at Mobile Pie I was asked to develop a small game that will be used in conjunction with other educational pieces to teach children more about the agriculture industry.

<!--more-->
-----
#### How did it go ?
Due to my experiences in university with using a purely code based engine I was right at home with Phaser 3. This was the first real time since I started placement to stretch my legs with some traditional OOP; since in PlayCanvas there isn't an innate way to use inheritance and the way we used it in Mobile Pie was a hacky fix. The project itself was very simple in which the user has 3 commands (move forward, turn clockwise and turn anticlockwise) and their task is to navigate the grid collecting all the wheat in the lowest amount of moves possible whilst avoiding obstacles. Even though I put in the functionality of loading additional levels in through JSON files, in the end the client only wanted a single as it was only going to be a short Mini-game.

Through this task I learnt a lot about UX and UI design. I made the main UI elements using Gimp and Inkscape and had to account for various resolutions as the game will be able to be played on all devices whether that be a tablet, phone or computer. Thankfully Chromes developer tools came in extremely handy here as it allows you to test on various user defined resolutions.

All in all I was extremely happy how this project turned out as I worked on it from start to finish as the main developer and had the core product finished within a two week sprint, Even though it ended up being slightly long than that due to further iterations based on the clients feedback.

Below are some gifs of the game being played:
{% include flexslider-general.html imageUrls=page.gameCarousel.urls imageCaptions=page.gameCarousel.captions %}