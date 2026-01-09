+++
date = "2025-12-05 05:30:35"
draft = false
title = "Vampire Survivor"
description = "2D, pixel style, C++ based vampire survival-like playable game"
[taxonomies]
tags = ["2D", "C++", "Game", "Project"]
[extra]
image = '/images/VS.png'
+++

![Infinite](/images/infinite.png)

<strong>Assets Annnoucement</strong>

Mainly acquired from itch.io, free assets. Fonts is drawn by author.

<strong>Game Design</strong>

Player can make use of mountain to avoid or kill other three types of enemies efficiently. However, mage's light ball is forcing player to run, find and kill mages. The design partially inherits the pleasure of killing huge amount of enemies by certain strategy, also applies survive pressure to make this game challenging, like vampire survivors.

The health of player is set to 10, every time collide to an enemy or shoot by mage (a kind of NPC), player losing one health. Once it dropped to zero, player dies. The collided enemy will die as well. Player can press WASD to move, press R to cast AOE 5 damage to top 3 nearest enemies in range, press B to save if user is afraid of dying soon. Player will automatically shoot arrow to nearest enemy that can penetrate enemies to deal tons of damage (if they are in a line). Both player's AOE and arrow attack are ranged, about half of the screen.

There are four terrain types: Road, Grass, Water, and Mountain. Water and mountain is a terrain that prevent player to move, yet water cannot stop NPCs. Grass will decrease all character's speed. What's more, item will increase the amount of player's AOE targets or decrease the arrow attack cooldown time. Mountain is quite unique, it has special interactions with characters.

Enemies have four categories as well. Mage, Runner, Tank and Normal. Mage is in 5 health, and capable to shoot light sphere that can penetrate the mountain, yet player's arrow cannot. Mage's attack range covered all screen. Runner is running faster, with also 5 health, trying to collide with player directly. Tank has 15 health, relative slow speed to normal type. Normal type has the same attributes with player. 

<strong>Play Method</strong>

Requiring Visual Studio, download zip from github, unzip and run directly by visual studio. Console choosing new/load and fixed map and infinite map.

personal github Link [<strong>2D Game</strong>](https://github.com/GEShunyuYang/Game_VampireSurvivors)