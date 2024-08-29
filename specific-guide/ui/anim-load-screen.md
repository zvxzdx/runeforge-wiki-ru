---
title: Animated Loading Screen
description: How to make Animated Loading Screen
published: true
date: 2024-08-29T20:24:07.036Z
tags: 
editor: markdown
dateCreated: 2024-08-29T20:24:07.036Z
---

# **Custom Animated Loading Screen Guide**

Learn how to create a custom animated loading screen for League of Legends by following this comprehensive step-by-step guide. Whether you're a beginner or an experienced modder, this guide will help you

## Video Tutorial

If you prefer a visual guide, you can follow the step-by-step video tutorial available on YouTube. The video will walk you through the entire process.

<div align="left">
  <a href="https://www.youtube.com/watch?v=9Mz6xG-CBV8"><img src="https://img.youtube.com/vi/9Mz6xG-CBV8/0.jpg" alt="How to make Animated Loading Screen"
style="width:75%"></a>
</div>

## Step 1: Download the Files
First, download the necessary files.
- [**Download Files**](https://www.mediafire.com/file/aptcxtcvcnp73jh/Animated_Loading_Screen.zip/file)
{.links-list}
## Step 2: Extract the ZIP File
Extract the downloaded ZIP file into a folder.

## Step 3: Extract the Folder Contents
Extract the contents of the folder into two main categories: `UI.wad.client` and `programs`.

## Step 4: Prepare Your Video
- The video duration **cannot be fractional** (e.g., 5.2 or 8.3).

> **Note:** Make sure your video resolution is exactly 720p and the frame rate is 30 fps to avoid any issues during the conversion process.

## Step 5: Convert Your Video
- Drag and drop your video onto the `VideoToSpritesheet.exe` file.
- Wait for the conversion to complete.

    ```bash
    Your mp4 file now should be converted to spritesheet.png
    ```

## Step 6: Do Not Close the CMD Window
- After the video is converted, **do not close** the CMD window.
- The information in the CMD window is important.

## Step 7: Rename the File
- Rename the `uibase` file located in the `UI.wad.client\clientstates\loadingscreen\ux\loadingscreenclassic` folder to `uibase.bin`.
    ```bash
    uibase -> uibase.bin
    ```

## Step 8: Convert BIN to PY
- Drag and drop the `uibase.bin` file onto the `rito_cli.exe` file located in the `programs\bin` folder. This will convert your file to `.py` format.

## Step 9: Edit the PY File
- Open the `.py` file and replace the values at the bottom with the values from the CMD window.
![image.png](/user-pictures/sirdexal/image.png)
## Step 10: Save and Reconvert the File
- Save the file.
- Delete the `uibase.bin` file and drag the `.py` file onto the `ritobin_cli.exe` file. This will reconvert your file to a `.bin` format.

## Step 11: Rename the File Again
- Remove the `.bin` extension from the `uibase.bin` file. The file should be named `uibase`.
    ```bash
    uibase.bin -> uibase
    ```

## Step 12: Convert the Spritesheet to DDS
- Convert the spritesheet file to a `.dds` format using an image editing tool.

## DDS Guide
- [For Photoshop](/core-guides/tools/adobe/photoshop)
{.links-list}
>**Note:** GIMP and paint.net comes with built-in support for DDS files, so you don't need to install any additional plugins. You can directly open, edit, and export DDS files using the default installation.

## Step 13: Convert the DDS to TEX
- Drag and drop the `spritesheet.dds` file onto the `tex2dds.exe` file located in the `programs` folder.

## Step 14: Move the TEX File
- Move the resulting `spritesheet.tex` file to the `UI.wad.client\assets\Animatedloadscreen` folder.

## Step 15: Create a New Mod
- Use `cslolmanager` to create a new mod and add the `UI.wad.client` folder to your mod.

## Step 16: Run the Mod and Enjoy
- Run your mod and enjoy your new animated loading screen!

## Further Reading
- [Official League of Legends Modding Documentation](https://developer.riotgames.com/docs/lol)
- [RuneForge Modding Community](https://www.runeforge.io)

## Conclusion
By following these steps, you should now have a fully functional custom animated loading screen for League of Legends. Enjoy your new creation and feel free to share it with the community!
