---
layout: post
title: "Generating Procedurally"
date: 2017-12-02 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Infinite Runner
img: runner_picture.jpg
thumb: c_thumb.jpg
published: true
---

## Jumping down, blocks to come

After getting the jump working next thing is to spawn blocks.

<!--more-->
-----
### Thoughts on how I want them to spawn

As for the blocks spawning themselves I want a small choice of blocks to spawn depending on the previous block that spawned. For example if the last block that spawned was one that was just on the ground, the next option I would like to spawn would either be another block of the same type or one that is 100 pixels higher. This way the spawning isn't completely random and I can ensure that the possible permutations are compatible with each other. By using the newer version of random functions I can specifically chose from a distribution. With this ability I can simply tag different heights of blocks with a different number then spawn them by having a Procedural generation machine return different numbers linked to the block heights.

An example of the generation idea:

```C++
if(last_block_spawned == BlockType::HIGHBLOCK)
{
  //spawn a low or v low block
  block_type = randomNumberGenerator(2, 3);
  return block_type;
}

int randomNumberGenerator(min, max)
{
  int rand_number = 0;

std::random_device rand;
std::mt19937 eng(rand());

std::uniform_int_distribution<> specified_dist(min, max);

rand_number = specified_dist(eng);

return rand_number;
}
```
