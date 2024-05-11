---
title: How to Transfer Animations from One Champ to Another (AKA Animation Retargeting)
description: This guide will show you how to transfer an animation unto another character
published: true
date: 2024-05-11T18:04:07.434Z
tags: animation, champion, retargeting
editor: markdown
dateCreated: 2024-05-11T18:04:07.434Z
---

# Required Tool
-   [Obsidian *Main program to extract and browse Leagues gamefiles.*](/core-guides/tools/obsidian)
{.links-list}

AND
-   [Blender *Program to create, edit, animate or rig 3D models*](/core-guides/tools/blender)
{.links-list}

OR
-   [Autodesk Maya *Program to create, edit, animate or rig 3D models*](/core-guides/tools/maya)
{.links-list}

I will be using Maya for this guide

# Tutorial
This tutorial will teach you how to do Animation Retargeting, which is, in short, reusing an existing animation and porting it to another skeleton.

In my case, I will be putting Star Guardian Ahri's dance into Ornn

From now on, Ahri will be the Main SKL, and Ornn the Targeted SKL

## Getting Main SKL in Maya

You will first want to import the Main SKL into the scene with the desired animation (in my case, the dance).

Import the skn by going to File > Import, changing the "Files of type" to "League of Legends : SKN" and importing your skn. 

![1.png](/user-pictures/goat/retargetanimation/1.png =x400)

You will then want to import the desired animation. To do so, go to File > Import, changing the "Files of type" to "League of Legends : ANM" then looking for the desired animation. In the import settings, make sure to select "Framerate Import : Override to Match Source" and "Animation Range : Override to Match Source"

![2.png](/user-pictures/goat/retargetanimation/2.png =x500)

Next select the "Root" bone and add a prefix. Go to Modify > Prefix Hiarchy Names

![3.png](/user-pictures/goat/retargetanimation/3.png)

And put anything you want there (I'll put Ahri_ because it looks clean)

![4.png](/user-pictures/goat/retargetanimation/4.png)

## Getting Targetted SKL in Maya

Now that the Main SKL is all cool and good, lets get the Targeted SKL in Maya as well. To do so, do the same thing as before : File > Import, and find the desired skn to import.

![5.png](/user-pictures/goat/retargetanimation/5.png =x400)

Now that we have both skeletons in the scene, lets begin the Retargetting! 

First, make sure that the arms are parallel to each other, this is necessary for the Retargeting to work. The Targetted SKL should have the same arm angle as the Main SKL, so if the Main SKL's arms are in A-Pose, put the Targetted SKL in A-Pose a well. You would do the same for a T-Pose.

![8.png](/user-pictures/goat/retargetanimation/8.png =x400)

Lets hide the mesh and skeleton from the Main SKL first by going into the outliner, selecting the mesh and skeleton, then pressing H. They should now be grayed out.

![6.png](/user-pictures/goat/retargetanimation/6.png =x400)

Click the little t-posing dude in the top right corner of maya, and then "Create Character Definition"

![7.png](/user-pictures/goat/retargetanimation/7.png)

You will now see a big scary man appear! Click that little bone icon right above the Viewport, it will allow you to see the bones trough the mesh.

![9.png](/user-pictures/goat/retargetanimation/9.png =x400)

It is now pretty straight forward, you double click on the arm of the scary man, then click on the bone corresponding on the Targetted SKL skeleton. EXEMPLE: The left shoulder with the left shoulder, etc.

When double clicking the scary man's shoulder, you will notice that the rest of the bones get grayed out. Like so : 
![10.png](/user-pictures/goat/retargetanimation/10.png)

This means that you have selected the bone succesfully.

Now, I would click the left shoulder of the Targetted SKL, since that is the bone I selected on the scary man.

![11.png](/user-pictures/goat/retargetanimation/11.png =x400)

Both left arm and right arm should now turn green on the scary man, this means that the bone was assigned succesfully.

![12.png](/user-pictures/goat/retargetanimation/12.png)

You will also notice some arrows pointing down on the scary man. Those are there to select the Clavicles, Fingers, Toes, Spine and Neck. It is important to fill them out of you want the animation retargetting to be better!

In the end, it should look like something like this :

![19.png](/user-pictures/goat/retargetanimation/19.png =x600)









