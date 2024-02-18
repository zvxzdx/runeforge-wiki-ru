---
title: Substance Painter 3D Guide
description: A full overview on how to use Adobe Substance Painter 3D.
published: false
date: 2024-02-18T20:26:23.473Z
tags: guide, maya, texturing, adobe, substance, painter, drawing
editor: markdown
dateCreated: 2024-02-18T20:05:08.131Z
---

This is an overall comprehensive guide for beginners on how to use Substance Painter for the sole purpose of painting textures for your creations. Lessons here can obviously be applicable outside of League skins, but this will specifically be geared towards that workflow.

# Required Tools

- [Maya *3D Modeling software*](/core-guides/tools/maya)
- [Adobe Substance Painter *3D texture painting software*](core-guides/tools/adobe/substance-painter)
- [Nvidia Texture Tools or Intel Texture Works *To export as .dds format*](/core-guides/tools/adobe/photoshop#intel-texture-works)
{.links-list}

# Written Steps

## Prepare the model for Substance Painter

**1.** 
The first thing we need to do before we even open the program is to make sure our mesh is ready. All normals must be facing outwards.

In Maya, to check our face normals, select your object in face mode and then hold right <kbd>click</kbd> + <kbd>shift</kbd> and drag your mouse to `face normals > toggle face normal display.` If your normals are flipped correctly, you should see the green sticks facing out from the faces. If your normals are reversed you will likely see small green dots or nothing at all.

If your normals need to be reversed, go to `mesh display > reverse.`

![reversenormals.webp](/user-pictures/vector/general-guides/substance-guides/reversenormals.webp =x1200)

**2.**
Our entire model must also be one material. You can set different materials for different parts on the model as you like, however you will need to combine the textures in a photo editing software such as through Photoshop or Gimp equivalent after you have finished painting.

Sometimes it isn’t necessary as some champions have more than one texture set.

Base Graves for example only has one for his model so I would use one material and get one texture file on export.

Seraphine however has three textures: one for her entire body, separate one for her hair, and one for her ultimate’s speakers. So with Seraphine I will have three materials set accordingly in my 3d program and I will get three texture files when I export.

You can always add more than one material via the champion’s bins.

![matsgraves.webp](/user-pictures/vector/general-guides/substance-guides/matsgraves.webp =x1000)

**3.**
When you open Adobe Substance 3D Painter and start a project with a new FBX (for multiple materials) model, you get both a 3D and 2D view (UV). 

On the top right of your screen you should see something that says `Texture Set List.` This is where all of your materials will be located. In most cases you will only need one but some champions have two or more as stated in **step 2** on **PREPARING THE MODEL FOR SUBSTANCE**. You can hit the eye to toggle visibility on each material.

You will also see `Properties` which is where you can adjust your brush texture and other attributes. This can also be found on the top left of the UI for ease of access. And then there’s “Layers” which is self explanatory.

> Interface will differ depending on your version of the program - the version in the pictures is older.
{.is-info}

![modelp1.webp](/user-pictures/vector/general-guides/substance-guides/modelp1.webp)

1. If your model’s faces are correct, it should appear as it does on the left picture. If your model or specific faces are flipped such as in the image on the right, then you must flip those faces in Maya (or other 3D software) and update the model in Substance (`edit > project configuration > select > [updated mesh] > OK`).

![modelp2.webp](/user-pictures/vector/general-guides/substance-guides/modelp2.webp)

2. Click on the tab just above the model where it says `Material` and change it to `Base Color` since that is all that League uses.

![modelp3.webp](/user-pictures/vector/general-guides/substance-guides/modelp3.webp)

# Sources

- Bearded Shepherd
