---
title: Prevent VFX from breaking
description: A guide on how to fix broken VFX and prevent them from breaking again.
published: true
date: 2024-02-21T21:08:17.473Z
tags: vfx, bin, fix
editor: markdown
dateCreated: 2024-02-21T21:08:17.473Z
---

> Work ahead!
> We want to write this guide out instead of linking videos. If you want to help us out: [Click here](/posting-guide/apply-as-contributor)
{.is-info}

This tutorial shows you how your particles should break less often by including every particle texture and model in your mod and rerouting them to your champion’s particle folder. This can also help you find all particles your champion/skin uses.

Particles break and have blocky shapes due to Riot renaming files that you might not have edited, but they are from the game files.If your .bins are not from the same patch as the file was renamed in, your particles will break as the old bin cannot find the outdated filename, resulting in often blocky shapes and missing models.

![showbrokenvfx.webp](/user-pictures/vector/general-guides/fix-sfx/showbrokenvfx.webp)

# Required Tools
Bin Converter:
- [Ritobin *Tools to translate bin files into Python files*](/core-guides/tools/rito-bin)
{.links-list}

An code editor of your choice:
- [Select any Code editor here](/core-guides/tools#code-bin-editing)
{.links-list}

If you choose Visual Studio Code, you need the [Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python) aswell!
*Other editors work aswell, aslong as they can edit .py (Python) files.*

- [Hacksaw *Visual Editor by Marcius*](/core-guides/tools/hacksaw)
{.links-list}


# Video Guide
<br>

<div align="left">
  <a href="https://www.youtube.com/watch?v=6FLj7f9_fRE"><img src="https://img.youtube.com/vi/6FLj7f9_fRE/0.jpg" alt="Guide on how to fix broken vfx and prevent them from breaking"
style="width:75%"></a>
</div>

*External link to Youtube!*
# Sources

- Yoru Queen of Night