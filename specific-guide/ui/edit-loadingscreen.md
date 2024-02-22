---
title: Customizing the Loadingscreen
description: A guide collection of different ways to customize loadingscreens.
published: true
date: 2024-02-22T20:09:27.046Z
tags: guide, ui, loadingscreen
editor: markdown
dateCreated: 2024-02-22T18:42:08.415Z
---

# Create custom loadingscreen

This guide teaches you how to change the loading screen background to any background you like.

## Required Tools

- [Any 2D editing program *Any tool which can handle .dds files*](/core-guides/tools#texturing)
- [Template *External Link*](https://www.mediafire.com/file/ulwhlqwju0ab5tz/Loading_Screen_Template.zip/file)
{.links-list}

<br>
<div align="left">
  <a href="https://www.youtube.com/watch?v=WbR6AMlCK8w"><img src="https://img.youtube.com/vi/WbR6AMlCK8w/0.jpg" alt="Guide on how to edit VFX Color values via code"
style="width:75%"></a>
</div>
*External Youtube Link!*

>During events like worlds, there will be a different loading screen that you can also replace. Theoretically you can replace any loading screen as long as you can find it in obsidian (urf, tft, etc). I will not be covering these, though.

# Custom loadingscreen spinner
# Tabs {.tabset}
## Photoshop

### Breaking down gifs frame by frame

First off all, what we want to do is split our gif or video into single individual frames. You can use [Bloggif](https://es.bloggif.com/gif-extract) for this if you're planning to use a GIF.

Once we have the gifs broken down into images, you have to pick exactly 32 of them. Keep in mind that you can repeat frames if you're just short of 32.

Next you're going to open your graphic editor of preference (In this guide [Photoshop](/core-guides/tools/adobe/photoshop) will be used). Bear in mind that the graphic editor must be able to handle transparent backgrounds, as we're working with sprites.

 
### Placing the frames in the template

After you finish importing ["Guide Photoshop.psd"](https://www.mediafire.com/file/4u5xju7f0ntpddf/Gu%25C3%25ADa_Photoshop.psd/file) or ["Guide PNG"](https://www.mediafire.com/view/q4eu2vtq7z7jrrj/Gu%25C3%25ADa_PNG.png/file) into your graphic editor of choice, you'll begin placing every frame in their respective slot.

The red bar counts as the limit of each frame. Feel free to occupy as much space in every individual block as you can.

Once done, we have to get rid of the template and save the file as a .dds using the [Intel&reg; Texture Works](/core-guides/tools/adobe/photoshop#intel-texture-works) or [Nvidia Texture Tools](/core-guides/tools/adobe/photoshop#nvidia-texture-tools).
If you aren't using Photoshop you can use [this online converter](https://www.convertidor.es/png-a-dds#:~:text=Como%20convertir%20de%20PNG%20a%20DDS%3A%20Convertidor%20de,Pulsa%20en%20Descargar%20para%20obtener%20tu%20archivo%20convertido) or any other application that can save a DDS file.

 
### Converting .dds files to .tex

You will need to convert the [.dds](/core-guides/filetypes#dds) file to [.tex](/core-guides/filetypes#tex). You will need [tex2dds](/core-guides/tools/tex2dds) for this.

When the conversion is done, we'll change the name of the file to "loadingscreen_spinner_atlas" (without quotations). After that, you will want to create a few folders. It should look something like this:
<kbd style="background-color:#343942">[FOLDER WITH YOUR MOD NAME]/assets/ux/loadingscreen/loadingscreen_spinner_atlas.tex</kbd>

## paint.<span></span>net

### Breaking down gifs frame by frame

First off all, what we want to do is split our gif or video into single individual frames. You can use [Bloggif](https://es.bloggif.com/gif-extract) for this if you're planning to use a GIF.

Once we have the gifs broken down into images, you have to pick exactly 32 of them. Keep in mind that you can repeat frames if you're just short of 32.

Next you're going to open your graphic editor of preference (In this guide [paint.net](/core-guides/tools/paint-net) will be used). Bear in mind that the graphic editor must be able to handle transparent backgrounds, as we're working with sprites.

### TBD

# Sources

- Tyre
- LxVer