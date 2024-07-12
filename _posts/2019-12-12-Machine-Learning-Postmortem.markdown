---
layout: post
title: "Tensorflow Post Mortem"
date: 2019-12-12 12:00:00
author: Alexander Allman
categories:
- Blog
- Advanced Technology
- Tensorflow
- Keras
- Python
img: tensorflowBanner.png
thumb: tensorflow.png
published: true
projectCarousel:
    urls:
    - "/assets/carouselImages/machineLearningPostMortem/imageFetch.gif"
    - "/assets/carouselImages/machineLearningPostMortem/imageSplit.gif"
    - "/assets/carouselImages/machineLearningPostMortem/levelBuild.gif"
    captions:
    - "Fetching images from the MapQuest API"
    - "Dividing an image into smaller defined chunks"
    - "Importing the resultant JSON into Unity"
---

### Machine learning!

Hot off the heels of DirectX I'm now moving onto a task utilising Tensorflow and Keras.

<!--more-->
-----
For the second task in the Advanced Technologies module I've been tasked to make a CNN that can identify elements in a satellite image and then reproduce it as a game world in Unity. For this task I had to use various things that I was mostly new to. These included using Tensorflow and Keras in python, using GET requests in python to fetch satellite images in bulk and using cv2 and numpy to break up those images into smaller chunks for the CNN to identify. To see my dev blogs of this task follow the link below to my video playlist.

Click [Here](https://www.youtube.com/playlist?list=PL8qSAz12sGSGkJyQpBiwZyp3kzerEl5oG) to be taken to the playlist.

#### How did it go?
This project got off to a blazing start and tapered off towards the end. In the beginning significant progress was being made each week on the project such as setting up the CNN, creating a script that fetches satellite images and the script that divides those images into smaller chunks. After this however, visible progress slowed significantly as I had to categories thousands of images for the classifier to use and train what totaled to hundreds of different models to find which one gave the most accurate result. Thankfully myself and two other colleges helped each other by categorising a third of the images each; helping all three of us keep our sanity.

The Unity implementation in it's current state is fairly simple. I created a python script that uses a model created beforehand and a file path to an image. The script then breaks the image up into chunks of desired size and classifies each chunk of the image. It then takes the result of the classification and the X and Y iterations of the two for loops to create co-ordinates for the classification. All this information is then output to a JSON file; which is then read into Unity and appropriate prefabs are instantiated at the positions based on the classifications.

Some gifs can be seen below of the various features:
{% include flexslider-general.html imageUrls=page.projectCarousel.urls imageCaptions=page.projectCarousel.captions %}


#### What improvements will be made?
Overall I'm very happy with how the project turned out, however, there are some improvements I would like to make to the Unity implementation:
    - Flesh out the prefabs with assets to make the created world prettier.
    - Extend the script that instantiates prefabs to replace classifications that don't make 100% sense. For example a break in the middle of a road.
    - Make or utilise a tile system so that when the prefabs are placed in the world they join up correctly.
