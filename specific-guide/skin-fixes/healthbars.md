---
title: How to manually fix healthbars
description: A short tutorial on how to fix healthbars if FixHealthBar.exe doesnt work.
published: true
date: 2025-02-18T08:02:37.507Z
tags: guide, skin fix
editor: markdown
dateCreated: 2025-01-28T18:37:13.690Z
---

# How to fix healthbars
> This tutorial uses LtMAO, specifically the explorer contexts. If you dont have it installed, follow the instructions [here](/core-guides/tools/LtMAO#explorer-contexts).
> {.is-info}

---
Examples of broken healthbars
~unitHealthBarStyle=10~
![hpbarexample1.png](/user-pictures/fbs/hpbarexample1.png)
~unitHealthBarStyle=9~
![hpbarexample.png](/user-pictures/fbs/hpbarexample.png)

---
## How to fix them

Navigate to your cslol installed directory and find the name of your mod. Inside that, navigate to your WAD directory and extract your wad using LtMAO.

![extract-wad.png](/user-pictures/fbs/extract-wad.png)

Now you got a directory named ```champion name.wad```
Inside that directory, navigate to ```data\characters\champname\skins```. Inside that directory you will see one or more .bin files. Convert them to .py with LtMAO, then open the .py in your text editor.

![convertbintopy.png](/user-pictures/fbs/convertbintopy.png)

In your text editor press ctrl+f and search for ```unitHealthBarStyle```, it will look something like this:

![hpbarstyle9.png](/user-pictures/fbs/hpbarstyle9.png)

Change that number to 11 and save your file. Next, you will need to convert your .py back into .bin.

![pytobin.png](/user-pictures/fbs/pytobin.png)

Following this, you need to delete the .py file, then navigate to your WAD directory and convert the ```champname.wad``` directory back to a .wad.client. 

![packtowad.png](/user-pictures/fbs/packtowad.png)

After this, you need to delete your ```champ.wad``` directory, restart cslol-manager and youre good to go!
![excited-kitty.png](/user-pictures/fbs/excited-kitty.png)


