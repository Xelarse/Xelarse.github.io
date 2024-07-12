---
layout: post
title: "TweetCards Post Mortem"
date: 2019-12-10 12:00:00
author: Alexander Allman
categories:
- Blog
- Mobile Applications
- XCode
- Twitter REST API
img: tweetCardBanner.png
thumb: tweetCard.png
published: true
projectCarousel:
    urls:
    - "/assets/carouselImages/tweetCardsPostMortem/navMenu.gif"
    - "/assets/carouselImages/tweetCardsPostMortem/addCard.gif"
    - "/assets/carouselImages/tweetCardsPostMortem/openTimeline.gif"
    - "/assets/carouselImages/tweetCardsPostMortem/openReplies.gif"
    - "/assets/carouselImages/tweetCardsPostMortem/deleteCard.gif"
    captions:
    - "Navigating the menu"
    - "Card creation"
    - "Selecting a card to view it's timeline"
    - "Selecting a tweet to view it's replies"
    - "Editing and deletion of cards"
---

### Custom Twitter Timelines!
For Mobile Applications I was tasked to make any app of my choice. To take a break from games development I decided to make an app utilising Twitters API.

<!--more-->
-----
The core premise of this app was to allow the user to create custom timelines; Each timeline would just contain a few select accounts it gets tweets from and the user could create as many of these as they wanted. For example, the user could have one card just for following news accounts and another for just following game developers. This way if the user wanted to see the news they wouldn't have to filter through the tweets of game developers. This app was inspired by TweetDeck but by making it native to the device, the user experience can be improved through gesture control and by following Apples human interface guidelines.

#### How did it go?
This project was quite a tough one. Even though we we're only delivering a vertical slice I still wanted my app to be feature rich and as near to completion as possible. In addition to this it was also the first time I was dealing with GET and POST requests of Twitters REST API and programming in Swift. The project overall though was certainly rewarding however. Seeing the app I created working as I designed it to was a big boost to confidence after tackling these new topics.

Some gifs can be seen below of the app in use:
{% include flexslider-general.html imageUrls=page.projectCarousel.urls imageCaptions=page.projectCarousel.captions %}


#### What improvements will be made?
The project itself was a vertical slice, so theres certainly improvements to be made:
    - Add the ability to fullscreen view photos and videos on Tweets.
    - Embed Retweets into its own view so that it's clearer whats a Tweet and whats a Retweet, similarly to how Twitter does it currently.
    - Add the ability to set an image or a custom colour to cards so that the user can know which card is which without having to read it's title.
    - Various UX improvements mentioned in the user testing video which can be found [Here](https://youtu.be/LOpY_wx8I8s)
