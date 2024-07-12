---
layout: post
title: "Initial progress update"
date: 2018-04-03 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Networking game
img: networkingBanner.png
thumb: networking.png
published: true
---

### Progress has been made!

After coming from the previous assignment reasonably happy with the results I set out to start this one just as strongly!

<!--more-->
-----
#### Units now have types!
So that I could avoid having multiple short stub children of a unit class for the variety of units, I have instead opted to just have a unit and then give the unit a type.

I have implemented this logic along side a json parser in order to quickly have the ability to add new unit types, change sprites and balance stats. This allows for the developer to very easily change and balance aspects of each class without having to delve deep into classes and by using the concept of a unit having a type, it avoids lots of classes with very little difference between them.

Below is an example of the json file that will contain all the various units:

[![https://gyazo.com/0162927a292dccbdbe9d488c8e42aef4](https://i.gyazo.com/0162927a292dccbdbe9d488c8e42aef4.png)](https://gyazo.com/0162927a292dccbdbe9d488c8e42aef4)


---
#### Full scene manager rework!
Following feedback from my previous assignment I have rebuilt my scene manager. Firstly this was done due to the previous scene manager not actually initialising the scenes, all it really did was render them, which at that point could've been done in the main game. Lastly as the game got more and more complex my state machine continued to get more and more convoluted which became hard to read and understand for outsiders. This also lead to tight coupling between the scene manager, main game and the state machine.

Now however it works quite differently. Instead of the game managing inputs and passing them into a state machine, each scene itself has it's set of event listeners for inputs. All this scenes are then initialised and stored in a vector by the scene manager. Finally the last thing in the scene managers vector is the one that gets rendered and updated. This means we can very easily stack scenes onto each other and then pop them off one by one to get back to previous scenes.

This works great when transitioning between scenes as when your done with a scene you can simple pop off the back one to go back to the previous one; once there's no more in the vector the game then ends. This also fixes the problem with the previously messy state machine managing inputs because each scene is it's own class with it's own logic for processing inputs. Each scene also has a pointer to the scene manager that is holding it so that it can prompt the scene manager for various scene changes within the scenes themselves, freeing up coupling from the main game cpp and allowing scenes to seamlessly transition between each-other, through each-other.

The only down side to this is having to remember to either disable event listens unregister them outright, otherwise some scene logic can be processed even if said scene isn't the last one currently on the vector.

Below is an example of how the scene manager updates and renders the appropriate scene:

```C++

SceneManager::update()
{
  if (scene_vector != 0)
  {
    scene_vector.back()->update();
  }
  else
  {
    exit_game = true;
  }
}

SceneManager::render(ASGE::renderer* ren)
{
  if(scene_vector != 0)
  {
    scene_vector.back()->render(ren);
  }
}

```
