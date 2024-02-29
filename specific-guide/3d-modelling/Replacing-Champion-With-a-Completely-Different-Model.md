---
title: Replacing Champions With a Different Character
description: This tutotial will show you how to replace the model from a champion with another one
published: true
date: 2024-02-29T02:01:05.953Z
tags: modelling
editor: markdown
dateCreated: 2024-02-29T02:01:05.953Z
---

# Replacing Champions With a Different Character
This guide will help you in replacing your champion with a new character, like a character from another game. It would also work with other league champions!

# Required Tools
- [Obsidian *Main program to extract and browse Leagues gamefiles.*](/core-guides/tools/obsidian)
{.links-list}

And

- [Maya 2023 *Program to create, edit, animate or rig 3D models*](/core-guides/tools/maya)
- [LoL-Maya *Plugin made by tarngaina*](https://github.com/tarngaina/lol_maya)
{.links-list}

OR
- [Blender *Program to create, edit, animate or rig 3D models*](/core-guides/tools/blender)
{.links-list}

I will be using Maya for this guide.

# Guide
## Finding your model
What you will want first is choosing a character you want and finding a model for it. For this guide, I will be swapping Zeri with Cuphead!

You might be able to find your character by searching "(Character Name) 3D model" in google. If you cannot find it, you might have to create it yourself!

Here are a few sites to help you find some cool models :

- [Model Ressource](https://www.models-resource.com)
- [Deviant Art](https://www.deviantart.com)

## Setting-up your model
First, I would recommend loading your new model in an empty scene, to check if everything is in order

If your model has no .skl and is standing upright in the middle of the scene, then you won.

![11.png](/user-pictures/goat/custommodels/11.png =x400)

<details>
<summary>If lose</summary>
<br>
  
![1.png](/user-pictures/goat/custommodels/1.png =x400)

Here my model is not upright and already has a skeleton (or an [.skl](/en/specific-guide/filetypes#skl), for simpler term). So I will first start by fixing those issues

If your model already has an .skl, you will first need to unbind it before doing any sort of movement. 

You will first select every part of your mesh, then, in the Rigging tab, you will find Skin > Unbind
![2.png](/user-pictures/goat/custommodels/2.png =x400)

You can then delete the .skl, it is no longuer needed.

After, you will want to make your character upright (if it isnt). It is possible that your mesh will have multiple different parts, this will complicates thing if you simply try to rotate it. 

First, group your meshes : select all your meshes by drag selecting then press ctrl+g or by going into Edit > Group 

![3.png](/user-pictures/goat/custommodels/3.png =x400)

This will create a group that you can select with a pivot in the center of your scene, allowing you to easily rotate your model! (You can hold "J" while rotating to rotate on hard angles)

![4.png](/user-pictures/goat/custommodels/4.png =x400)

With your model now boneless and standing straight, you can export it as an .fbx, an .obj or any other format Maya can read!

With the group or mesh selected, go to File > Export Selected and select the file type.

![5.png](/user-pictures/goat/custommodels/5.png =x300)![6.png](/user-pictures/goat/custommodels/6.png =x300)  
</details>

# Replacing the model

Now that we have our custom model ready, load your desired League champion into a new scene by drag and dropping the [.skn](/en/specific-guide/filetypes) in an empty scene (this will also import the [.skl](/en/specific-guide/filetypes) automatically)

I will then import Zeri, since this is the Champion I chose

![7.png](/user-pictures/goat/custommodels/7.png =x400)

You can then import your model also by drag and dropping it into the scene.

![8.png](/user-pictures/goat/custommodels/8.png =x400)

After importing, you might notice that you model isnt exactly the same size, might be bigger or smaller then your League champion. In my case, the model is way smaller. 

![9.png](/user-pictures/goat/custommodels/9.png =x400)

You will want to make sure it fits has best has possible. Something like shoulder to shoulder should be what you aim for. 

>Scale your model! Not the League champion!
>{.is-warning}

![10.png](/user-pictures/goat/custommodels/10.png =x400)

Once thats done, you can hide the champion model for now. In the Outliner, select the League champion and press H.

![13.png](/user-pictures/goat/custommodels/13.png =x400)

Now that the model is hidden, press the little Bone button so you can see your .skl through the model

![12.png](/user-pictures/goat/custommodels/12.png)
