---
title: Particle swapping through bin-editing
description: This tutorial teaches you how to take particles from one champion and reuse them on another champion.
published: true
date: 2024-02-22T04:29:01.767Z
tags: code, bin, particle
editor: markdown
dateCreated: 2024-02-22T04:29:01.767Z
---

# Particle swapping through bin-editing
This tutorial teaches you how to take particles from one champion and reuse them on another champion.

![reuse_particle.gif](/user-pictures/goat/reuse_particle.gif =x400)

## Required Tools
- [Ritobin *.bin to .py file converter*](/core-guides/tools/rito-bin)
{.links-list}
- [Hacksaw *Tool to visually edit bin files*](/core-guides/tools/hacksaw)

# TIPS
## BEST ORDER TO WORK ON PARTICLES TO MINIMIZE FUCKUPS
1. Look up skills that might be useful for your champion (skin previews etc.)

2. Extract the bins and textures/models etc. for those abilities

3. Copy all the particles folders of the other champions into your wad.client folder

4. Edit the bins to your liking

5. Check in-game

6. If you have buggy textures: Run your wad folder through bintex, open the “Missing” list and add any missing files to your wad folder – Tutorial

7. Make sure that you now have everything in-game

8. In .bins, reroute all your particle files to the base folder of your champion – Tutorial

9. Move all your particle files into the base folder of your champion

10. Hope everything is there, if not, check the “Missing” list again or the code directly and add missing files.

11. Done

# HOW TO MAKE YOUR PARTICLES BREAK LESS OFTEN
After finishing your particles I recommend following this tutorial.
Your skins will break less often and should only break when a new skin for the champion gets released.