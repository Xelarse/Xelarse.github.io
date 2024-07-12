---
layout: post
title: "Scene Manager Implementation"
date: 2018-02-10 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Birdman
img: birdman.jpg
thumb: c_thumb.jpg
published: true
---

## Scene Management

After finalising initial designs layouts for the game I set out to create a scene manager for the game.

<!--more-->
-----
### Nodes Nodes Nodes
The Larger concept with the scene manager is that there will be nodes that contain references to either text or GameObjects for their sprites. These nodes are then organised into different scenes and depending on what state the game is in different scenes are rendered. The state machine being used is a similar state machine to my previous projects.

The rendering of these different scenes however will not be dealt with in the game.cpp but in the scene manager itself, this will be done through the renderer and scenes being passed through by reference into the scene manager.

Here is a code snippet of how I plan to structure the scene manager class itself:

```C++
class SceneManager
{
    friend class game

    struct node
    {
      GameObject node_object;
      string text;
    }

    struct scene
    {
      vector<node> scene_renderables;
    }

    renderScene(renderer ren, scene& scene)
    {
        for (each node in scene)
        {
            if (there is a gameobject)
            {
              render GameObject;
            }

            else if (there is text)
            {
              render text;
            }
        }
    }

};
```
