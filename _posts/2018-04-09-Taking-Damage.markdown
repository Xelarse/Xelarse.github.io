---
layout: post
title: "Adding the ability for units to take damage"
date: 2018-04-09 12:00:00
author: Alexander Allman
categories:
- Blog
- Low-Level Programming
- Networking game
img: networkingBanner.png
thumb: networking.png
published: true
---

#### Adding the ability for units to take damage

As my other group members begin to add unit movement and the way to recognise that the user wants to attack. I'm going to implement a damage taking function

<!--more-->
-----
#### How it was done
Due to the game being based of Heroes of Might and Magic, there were various aspects to each unit that needs to be taken into account. These being: How many units are currently on that square (Squad Size), how much armour the units have and how much damage each individual unit deals. The idea is that the units damage is amplified by the Squad Size because it's the damage of an individual multiplied by the amount of individuals attacking. We then take the armour of the one being attacked and work out how much damage that reduces the raw damage by. Following this we then work out the actual damage dealt by taking the raw damage and minusing the damage mitigated.

#### How this affects health and squad Size
Once we have the amount of damage that is going to be dealt we need to make another calculation. This is because the health of a unit is the health that each individual has in the squad, not the squad as a whole. In order to calculate how many of a squad died during an attack and how much health the remaining individuals have I took the damage that was dealt and divided it by an individuals units health. The amount of times it fits in fully will be damage to the squad and the remainder will be damage to the front units health.

Below is a code snippet:
```C++
////Getting the damage the unit will take
float raw_damage =  Raw damage worked out by inividual unit damage multiplied my squadsize
float mitigated_damage = raw_damage * (armour / 100)
int damage_taken = raw_damage - floor(mitigated_damage); //Total damage taken taken is the raw damage minus the damage that was mitigated

////Working out remaining hp and how much squad is lost
int squad_damage = floor(damage_taken / health);
int health_damage = damage_taken % health;

health -= health_damage;
squad_size -= squad_damage;
```
