---
title: Replacing Champions With a Different Character
description: This tutotial will show you how to replace the model from a champion with another one
published: true
date: 2025-05-16T02:17:10.499Z
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

If your model has no [.skl](/en/specific-guide/filetypes#skl) and is standing upright in the middle of the scene, then you won.

![11.png](/user-pictures/goat/custommodels/11.png =x300)

<details>
<summary>If lose</summary>
<br>
  
![1.png](/user-pictures/moga/goat_model_swap/goat_model_swap_1.png =x350)

Here my model is not upright and already has a skeleton (or an [.skl](/en/specific-guide/filetypes#skl), for simpler term). So I will first start by fixing those issues

If your model already has an [.skl](/en/specific-guide/filetypes#skl), you will first need to unbind it before doing any sort of movement. 

You will first select every part of your mesh, then, in the Rigging tab, you will find Skin > Unbind
  
![2.png](/user-pictures/goat/custommodels/2.png =x550)

You can then delete the `.skl`, it is no longer needed.

After, you will want to make your character upright (if it is not already). It is possible that your mesh will have multiple different parts, this will complicates thing if you simply try to rotate it. 

First, group your meshes : select all your meshes by drag selecting then press ctrl+g or by going into Edit > Group 

![3.png](/user-pictures/goat/custommodels/3.png =x550)

This will create a group that you can select with a pivot in the center of your scene, allowing you to easily rotate your model! (You can hold "J" while rotating to rotate on hard angles)

![4.png](/user-pictures/goat/custommodels/4.png =x550)

With your model now boneless and standing straight, you can export it as an .fbx, an .obj or any other format Maya can read!

With the group or mesh selected, go to File > Export Selected and select the file type.

![5.png](/user-pictures/goat/custommodels/5.png =x300)![6.png](/user-pictures/goat/custommodels/6.png =x300)  
</details>

# Replacing the model

After saving your custom model, you can open a new scene and load your desired League champion by dragging and dropping the [.skn](/en/specific-guide/filetypes#skl) into it (this will also import the [.skl](/en/specific-guide/filetypes#skl) automatically)

![8.png](/user-pictures/moga/goat_model_swap/goat_model_swap_8.png =x400)

After importing, you might notice that your model isnt exactly the same size, might be bigger or smaller then your League champion. In my case, the model is way smaller. 

![9.png](/user-pictures/goat/custommodels/9.png =x400)

You will want to make sure it fits as best as possible. Something like shoulder to shoulder should be what you aim for. 

>Scale your model! Not the League champion!
>{.is-warning}

![10.png](/user-pictures/goat/custommodels/10.png =x350)

Once thats done, you can hide the champion model for now. In the Outliner, select the League champion and press H.

![13.png](/user-pictures/moga/goat_model_swap/goat_model_swap_13.png =x400)

Now that the model is hidden, press the little Bone button so you can see your .skl through the model

![12.png](/user-pictures/moga/goat_model_swap/goat_model_swap_12.png =x400)

## Cleaning up the skeleton

>This next step is optional, and I recommend doing it ONLY if you know what you are doing!
>{.is-warning}

<details>
<summary>Cleaning up the skeleton</summary>
<br>
You may notice that there are a lot of joints in the original model, but we dont really need all of those, it will make the next few steps slightly easier if we remove some of them.
  
For exemple : I dont need the bones for the coat, the hair and the fingers, so i'll be removing them.
  
Simply select the bones you want to remove and press backspace!
  
![14.png](/user-pictures/goat/custommodels/14.png)
  
Also, you may notice a few BUFFBONES here and there, do not delete those! These are used for the particles effect!
</details>

# Placing the bones
Now, you may have noticed the the bones dont really align with my character, so lets move them!

In general, you want the elbow bone where the elbow is, the hip bone where the hip is, etc...

You can use the Rotate tool to make them align with your character as much as possible. 

If, lets say, the arms are too long/too short, scale them to make it fit the skeleton

Make your character fit the skeleton as much as possible! Its going to influence the quality a lot!

------------------------BEFORE------------------------------------------------AFTER------------------------
![18.png](/user-pictures/goat/custommodels/18.png =x300)![19.png](/user-pictures/goat/custommodels/19.png =x300)

<details>
<summary>If your Champion has a weapon</summary>
<br>
Its fairly simple! For exemple, Yasuo has a sword : if I want to replace it, simply add your desired weapon over the weapon bone! 
  
![33.png](/user-pictures/goat/custommodels/33.png =x300)
  
And try to place it like the original weapon was, put it somewhere on the weapon bone, as close as possible to the original weapon's position.
  
![34.png](/user-pictures/goat/custommodels/34.png =x300)
</details>

# Binding the skeleton 
We will now bind the skeleton to our model! To do this, simply select your mesh/es and the Root of your skeleton, then go to the Rigging tab, Skin > Bind Skin and open the options by pressing the little square on the right side.

![20.png](/user-pictures/moga/goat_model_swap/goat_model_swap_20.png =x550)

Now that you are in the options, try to copy my settings here : make sure to bind to the Joint Hierarchy, set the max influence TO A MAXIMUM OF 4 (but I highly recommend 3, and go lower if your mesh doesnt have a lot of polygons/faces), and remove "Maintain max influences".

![34.png](/user-pictures/goat/custommodels/34.png)

Of course, make sure the deformation look good by rotating different joints, like the shoulders, the leg, the spine, etc.

If the first settings didnt do a good job, unbind the mesh first and try these ones instead. (the unbind option is at the same place as the bind skin option)

![35.png](/user-pictures/goat/custommodels/35.png)

# Weighting your character
I will not be going over this step, since its a pretty big one and we already have another tutorial for it!

You can follow Yoru's Weight Painting guide [here!](https://youtu.be/LxO4djdtxJg?si=D9QrBaDeyVQ_eaqu)

# Getting the new model in game
Once the Weight Painting is done, you are pretty much good to go! You can now export your new [.skn](/en/specific-guide/filetypes) and [.skl](/en/specific-guide/filetypes#skl) into your asset folder. Simply replace the .skn, the .skl will update automatically

![22.png](/user-pictures/goat/custommodels/22.png =x350)
![23.png](/user-pictures/goat/custommodels/23.png =x350)

>Remember to select League of Legends : SKN + SKL !

You can now drag the client folder into csLoL and run the program. Rename the folder containing your asset and data folder to (Champion Name).wad.client and just drag and drop it in csLoL, it should create a new mod.

![31.png](/user-pictures/goat/custommodels/31.png =x380)
![32.png](/user-pictures/goat/custommodels/32.png =x350)

You could now see your model in game!

![26.png](/user-pictures/goat/custommodels/26.png =x300)

A little strange tho...

## Getting the textures

Usually, when getting your model online, you should also have a texture file included with it.

![24.png](/user-pictures/goat/custommodels/24.png =x550)

Its possible that you will different weird files, we only want the colored ones. In my case, these 2.

![25.png](/user-pictures/goat/custommodels/25.png =x550)

Now in maya, assign the "Body" material to your mesh, since most if not all League champs have that material, the game will then be able to detect it and assign the right material to it.

Select your mesh, then, while holding right click, Assign Existing Material > Body

![27.png](/user-pictures/goat/custommodels/27.png =x500)

>If your original model has multiple different Materials, go follow this tutorial here! 
- [Create skins with multiple materials](/specific-guide/texturing/create-skin-with-multiple-mats)
{.links-list}

Lets also not forget to reverse the normals, or else your character is gonna look see through.

With your mesh selected, go to the Modeling Tab, Mesh Display > Reverse

![28.png](/user-pictures/moga/goat_model_swap/goat_model_swap_28.png =x550)

And also replace the texture file in your assets! Replace the Body texture, usualy Champ_base_tx_cm. The 2x and 4x are texture quality when you lower them in settings in game, so swap them too! Or else the skin will look strange in lower settings.

![29.png](/user-pictures/goat/custommodels/29.png)

>You will need to change your texture files to .dds first! To do that, you can use GIMP, Photoshop with the Intel Texture Works plug-in, or Photopea to export them as .dds!
>{.is-warning}

And thats the basics! You should now have your new model in game!

![30.png](/user-pictures/goat/custommodels/30.png)
