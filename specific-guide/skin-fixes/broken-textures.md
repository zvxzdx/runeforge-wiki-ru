---
title: A tutorial on how to fix Broken textures
description: A tutorial on how to fix Broken textures caused by riot changing dds to tex
published: true
date: 2025-02-21T00:39:45.141Z
tags: texture, skin fix
editor: markdown
dateCreated: 2025-02-18T03:42:17.638Z
---

# How to fix broken textures
> This tutorial uses LtMAO, specifically the explorer contexts. If you dont have it installed, follow the instructions [here](/core-guides/tools/LtMAO#explorer-contexts).
{.is-info}
---
Riot is slowly changing textures to tex, causing mods to break if they have outdated dds textures. This is a tutorial on how to fix them.

## 1. Find your mod in the cslol installed folder and extract the wad.
![ddstexwad.png](/user-pictures/fbs/ddstexwad.png)

## 2. Find your textures and convert them using LtMAO
If you find any 2x,4x files, delete them. After converting the files to tex, you can delete every dds file. If you get an error "Unsupported dds format", then convert dds to png, then png to dds and then dds to tex. U need to delete the png files just like the dds ones.
![ddstexdel.png](/user-pictures/fbs/ddstexdel.png)

## 3. Repack your wad, then restart cslol.
If the wad change date changes, you can delete your folder.
![backtowad.png](/user-pictures/fbs/backtowad.png)
![deletefolder.png](/user-pictures/fbs/deletefolder.png)

This should be it. if you did everything right, your textures should look good ingame.
![brad.png](/user-pictures/fbs/brad.png)



