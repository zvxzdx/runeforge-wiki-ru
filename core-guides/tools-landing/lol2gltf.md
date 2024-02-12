---
title: Lol2gltf
description: A guide on how to install and use lol2gltf
published: true
date: 2024-02-12T20:30:56.573Z
tags: guide, install, lol2gltf
editor: markdown
dateCreated: 2024-02-12T20:30:56.573Z
---

# Lol2gltf
This page will explain lol2gltf and its features
## Tool Instalation
> Download: [lol2gltf](https://github.com/Crauzer/lol2gltf/releases/download/3.0.3/lol2gltf_3.0.3.zip), [lol2gltfCLI](https://github.com/Crauzer/lol2gltf/releases/download/3.0.3/lol2gltf.CLI_3.0.3.zip) **(DOWNLOAD BOTH)**
[Github Page](https://github.com/Crauzer/lol2gltf/releases)
{.is-info}

- Create a folder called "lol2gltf"
 - Extract both <kbd>lol2gltf.zip</kbd> and <kbd>lol2gltf.CLI.zip</kbd> into the folder
- lol2gltf is now ready to be used by clicking "lol2gltf.exe"
>In order to be able to use lol2gltf you need to be able to  extract all the files using [Obsidian](/core-guides/tools-landing/obsidian)(check guide)
{.is-warning}

## Convert .skn to gltf
- Open <kbd>lol2gltf</kbd>
- Resize the window as needed then click on `Select Simple Skin`
- Select the .skn you extracted from Obsidian(if you extracted Kayn and you wanted his base skin for example, you would pick the <kbd>kayn.skn</kbd> from <kbd>assets/character/kayn/skin/base</kbd>
- After that, click `Select Skeleton` and select said skeleton(it should appear without searching)
![imagem_2024-02-12_152542217.png](/user-pictures/thisisquitter/blender_starting_guide/imagem_2024-02-12_152542217.png =x450)
- Following that, you need to select the textures for the champion. Most of them have only one, but you can encounter ones with more than 1 Material like Udyr or Kayn. Make sure to select the correct ones as most are pretty self explanatory *(<kbd>kayn_Base_Assasin_tx_cm.dds</kbd> is the assasin form for example, and both <kbd>_Base_Assasin_Mat</kbd> and <kbd>_Assasin Hair_Mat</kbd> use that same image)*
![imagem_2024-02-12_152137449.png](/user-pictures/thisisquitter/blender_starting_guide/imagem_2024-02-12_152137449.png =x450)
- You can also choose to add an animation if you wish to do so by scrolling and clicking `Add Animation`
- Once you got everything you want selected, click `GLTF` and select where you want the file to be exported to
![lol2gltftut.png](/user-pictures/thisisquitter/blender_starting_guide/lol2gltftut.png)
- The file is now exported where you selected with the <kbd>.glb</kbd> file format.
## Importing to blender
> When importing to blender, **ALWAYS PUT THE BONE DIR MODE** TO <kbd>Blender(best for re-importing)</kbd>
![imagem_2024-02-12_153307903.png](/user-pictures/thisisquitter/blender_starting_guide/imagem_2024-02-12_153307903.png =x270)
If you don't do it, when you re-import the skin, it will look wonky since the bones changed positions
![malformed_udyr.png](/user-pictures/thisisquitter/blender_starting_guide/malformed_udyr.png =x300)
{.is-warning}
## Exporting from .gltf to .skn
- Save the 3D Model in Blender as a GLTF 2.0  file
- Modify the following command to fit your files
`lol2gltf.CLI.exe gltf2skn -g "skin exported from blender" -m "league of legends .skn file"`
For my example, the command would be
`lol2gltf.CLI.exe gltf2skn -g "C:\Users\manue\Desktop\Nova pasta\briar_import.glb" -m "C:\Users\manue\Desktop\Nova pasta\SKIN EXPORT\briar_base.skn"`
- Go to the <kbd>lol2gltf</kbd> folder
- Click on the search bar, and type "cmd" as shown below
![imagem_2024-02-12_154159242.png](/user-pictures/thisisquitter/blender_starting_guide/imagem_2024-02-12_154159242.png)
- A command box should appear
- Paste the command from before
- If it worked, it created a <kbd>.skn</kbd> and <kbd>.skl</kbd> file on the export location you provided
![imagem_2024-02-12_154851922.png](/user-pictures/thisisquitter/blender_starting_guide/imagem_2024-02-12_154851922.png =x400)![imagem_2024-02-12_154903496.png](/user-pictures/thisisquitter/blender_starting_guide/imagem_2024-02-12_154903496.png)
###### If it didnt work, check the following
- Make sure there is only one single mesh, parented to one skeleton
- Make sure the command is correct, and no <kbd>"</kbd> are missing or spelling mistakes are made
- If you can't find the problem, don't hesitate to ask for help on Runeforge's discord
