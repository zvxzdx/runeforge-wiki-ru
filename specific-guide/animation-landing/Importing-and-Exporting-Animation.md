---
title: Importing and Exporting Animations
description: A guide on how to import animations in Maya and export then for League modding
published: true
date: 2024-02-12T04:08:08.246Z
tags: animation
editor: markdown
dateCreated: 2024-02-12T01:46:49.842Z
---

# Importing and Exporting Animations
This guide will help you import animations in maya and export them for League modding.

## Tools Needed
- Obsidian
- Maya (with LoLmaya)

### Before you begin animation stuff
I strongly suggest you first get familiar with how to import <a href="/en/specific-guide/filetypes#skn">.skn</a> and [.skl](/en/specific-guide/filetypes#skl).

## Importing

### Extracting what you need

Firstly, you want to extract your desired Champion folder with Obsidian (for this post, I will be working with Blitzcrank). 
![extracting_stuff.png](/user-pictures/goat/extracting_stuff.png =x400)
Once extracted, navigate to the location where you extracted it and find the animation folder (Should be something like assets\characters\character\skins\base\animations).

### Importing the animation in Maya

With the model in the scene (import the <a href="/en/specific-guide/filetypes#skn">.skn</a> and [.skl](/en/specific-guide/filetypes#skl) first), simply drag and drop the animation you want (should be <a href="/en/specific-guide/filetypes#anm">.anm</a>) to see in the viewport, and VOILA, you have your funny Blitzcrank walk in the Maya scene.
![cry_about_it.gif](/user-pictures/goat/cry_about_it.gif =x300)

## Exporting
### Setting up the timeline
Now, if you want to Export an animation, you will want to specify the frames you want to export. To do that, select the range you want to export in the timeline 
![timeline_show-off.png](/user-pictures/goat/timeline_show-off.png =x300)
Here, the animation lasts for 30 frames, so I will remove the frame "0" so it is not included in the export. To select the frames you want to export, make sure the two numbers are the same in both boxes, so I out 1/1 and 31/31 (this will change depending on YOUR animation lenght)
![timeline_specification.png](/user-pictures/goat/timeline_specification.png =800x)
The bar needs to be "full"

### Exporting the animation
To export, select file > Export All 
![export_all.png](/user-pictures/goat/export_all.png)

Then, select the animation you want to replace and make sure you export as <a href="/en/specific-guide/filetypes#anm">.anm</a>

![export_has_anm.png](/user-pictures/goat/export_has_anm.png =x400)

Annnnnd well done! You now know how to import and export animations for League models!



