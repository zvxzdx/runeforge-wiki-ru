---
title: Obsidian
description: A tool to explore and export .wad archives.
published: true
date: 2024-02-11T22:48:08.462Z
tags: obsidian, tool, export, explorer
editor: markdown
dateCreated: 2024-02-08T18:19:22.298Z
---

Obsidian is a tool to explore and export .wad files, which are the League of Legends game file packages. This tool was made by [Crauzer](https://github.com/Crauzer).

---

# Download and Install

- [Download Obsidian](https://github.com/Crauzer/Obsidian/releases)
{.links-list}

When installing the program, make sure that you have the latest release installed, you can confirm as such on github:
![githubobsidian.webp](/user-pictures/vector/new-post-guide/githubobsidian.webp)
Where you install the program by downloading the Obsidian [.zip](/specific-guide/filetypes#zip) file on GitHub.
When opening the [.zip](/specific-guide/filetypes#zip) file or when extracting it to a folder, simply open the Obsidian.exe file to start the program.

# How to use

## Finding local files

There are various different types of files one might wish to edit as a League of Legends modder, that being from Champions, Maps, etc. but for this tutorial, we will be using our very own Aatrox as reference. 


What we do is that we go to our League of Legends files, and find the relevant folder the .wad.client file is in for Aatrox.

If you saved your game directly in your `C:\` Drive, then it will be located in `C:\Riot Games\League of Legends\Game\DATA\FINAL\Champions` where you can find Aatrox in there.

Note: The "Champion.language_REGION[.wad.client](/specific-guide/filetypes#wadclient)" is for the local voice lines of the champion. Meaning that Aatrox.en_US.WAD.CLIENT is his English Voice Lines.

![finding_files.webp](/user-pictures/vector/new-post-guide/finding_files.webp)
Once you have found your file, simply copy the file path at the top of your file explorer so you can find it on Obsidian.

## Extract Files via Obsidian

Now, open Obsidian.exe and wait for it to load. Whereafter you go to the menu at the top, click the box icon and click open, where you paste in the file path you copied, and find the [.wad.client](/specific-guide/filetypes#wadclient) file you want to extract.

![open.webp](/user-pictures/vector/new-post-guide/open.webp)


From there you go through the file and find the textures, model or anything that you wish to edit on Aatrox. In our example, we just want his base textures which can be found under `Assets/Characters/Aatrox/Skins/Base`
Where we then click the boxes next to the files we wish to extract:

![extract.webp](/user-pictures/vector/new-post-guide/extract.webp)

From there we go back to the top menu under the box icon, and click “Extract Selected” where we select the folder that we want to extract his files in. 