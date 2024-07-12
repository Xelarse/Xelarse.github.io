---
layout: post
title: "Plant Generation Post Mortem"
date: 2019-11-06 12:00:00
author: Alexander Allman
categories:
- Blog
- Advanced Technology
- DirectX 11
- Plant Generation
img: plantGenBanner.png
thumb: directx.jpg
published: true
projectCarousel:
    urls:
    - "/assets/carouselImages/plantGenPostMortem/camera.gif"
    - "/assets/carouselImages/plantGenPostMortem/leafAmount.gif"
    - "/assets/carouselImages/plantGenPostMortem/leafMovement.gif"
    - "/assets/carouselImages/plantGenPostMortem/leafRotation.gif"
    captions:
    - "Camera window allows rotation of view"
    - "Buttons to add and remove leaves/petals"
    - "Sliders to rotate leaves/petals"
    - "Sliders to move and rotate the whole bunch of leaves/petals"
---

### Getting back into C++!

After a year out of university we're getting right back into C++ with a DirectX project for the Advanced Technologies module.

<!--more-->
-----
For the first task in the Advanced Technologies module I've been tasked to make a plant generator using the DirectX 11 SDK. This was quite the task to start off with as over my placement I wasn't programming in C++. To see my dev blogs of this task follow the link below to my video playlist.

Click [Here](https://www.youtube.com/playlist?list=PL8qSAz12sGSFd6sT0MrefneCVDds_Ws2G) to be taken to the playlist.

#### How did it go?
As a whole this task was definitely a challenge but was almost certainly the best way to get back into C++. From following some tutorials online I not only learned how to setup DirectX and leverage it capabilities but I also reinforced some parts of C++ I wasn't completely clued in on such as templating. The project makes use of ImGui to control the customisation features of the flower due to it being very quick to set up and very easy to make various windows for quick iteration.

In the current implementation of the project the user will be presented with the basics of a flower being the stem, leaves and petals. The user can then tweak the amount, position and rotation of both the petals and the leaves. Once the user has found a combination they are happy with; they can export this model out to an OBJ and an accompanying MTL file. Some gifs can be seen below of the various features:
{% include flexslider-general.html imageUrls=page.projectCarousel.urls imageCaptions=page.projectCarousel.captions %}


#### What improvements will be made?
In the near future various improvements will be added to the project:
    - Extra textures for both the leaves and petals.
    - Adding extra foliage types; such as grass and bushes.
    - Improve the UI to look more professional and cohesive once final settings are decided.
    - Physics based lighting for more accurate lighting of the object in DirectX.
