---
layout: post
title: "Journey To The World Cup Post Mortem"
date: 2019-04-08 12:00:00
author: Alexander Allman
categories:
- Blog
- Internship
- Mobile Pie
img: qatarBanner.png
thumb: qatarThumb.png
published: true
gameCarousel:
    urls:
    - "/assets/carouselImages/qatarPostMortem/game/board.gif"
    - "/assets/carouselImages/qatarPostMortem/game/seekAndFind.gif"
    - "/assets/carouselImages/qatarPostMortem/game/shortestPath.gif"
    - "/assets/carouselImages/qatarPostMortem/game/stadiumSpin.gif"
    captions:
    - "The Overworld board"
    - "Seek and find Mini-game"
    - "Shortest path Mini-game"
    - "Jumbled Stadium Mini-game"
---

### What path will you take to the world cup?
My largest project by far for Mobile Pie has been to create a mario party esq board game with the aim to educate it's players about the world cup and the country in which its being held, Qatar.

<!--more-->
-----
#### How did it go?
The Journey to making the game was a long and at times a tedious one. Through our agile development process many components of the game were scrapped and iterated upon to fit the clients standards. This was especially more difficult due to us working through a middleman to the main client rather than the main client directly. Whilst this had it's benefits and easily outweighed the negatives; this often resulted in situations similar to chinese whispers where the product that the client wanted wasn't always clearly translated. Resulting in reworking many different things that could've been simply done right the first time around.

Looking past these difficulties the project overall went very well. We fulfilled the brief and stuck to the core concept described in our GDD and in all honesty improved on it massively through various tweaks and iterations to different sections of the game.

In the final product the key aim to the game is to navigate the map to the 5 Mini-game tiles and win their respective Mini-game. Once you have completed them and gained all 5 keys from the Mini-games you will be able to walk down a new path to the center of the map and reach the world cup. The game is 1-4 players and has been designed around a 15-30 minute experience. The Mini-games involve sorting the pieces of a stadium back together in the right orientation, answering quiz questions, finding hidden glyphs in an image or calculating the shortest route to the destination. Each player will play all these Mini-games at least once during their run. The game was developed to be played in either English or Arabic; ensuring that all the various UI elements work with text that is left-to-right or right-to-left.

Here are some gifs from the game:
{% include flexslider-general.html imageUrls=page.gameCarousel.urls imageCaptions=page.gameCarousel.captions %}