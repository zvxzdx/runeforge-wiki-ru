---
title: Create models/ skins with multiple materials
description: A guide on how to bind multiple materials onto models in Maya.
published: true
date: 2024-03-06T18:17:41.137Z
tags: maya, modelling, texturing, multiple, material
editor: markdown
dateCreated: 2024-02-20T03:44:21.671Z
---

> Work ahead!
> We want to write this guide out instead of linking a video. If you want to help us out: [Click here](/posting-guide/apply-as-contributor)
{.is-info}

# Required Tools

### 3D Tool

- [Maya 2023](/core-guides/tools/maya)
{.links-list}

### Code/Bin Editor
- [Ritobin *.bin to .py file converter*](/core-guides/tools/rito-bin)
{.links-list}

And 

- [Visual Studio Code *Feature rich tool to read, create or edit code*](/core-guides/tools/visual-studio)
{.links-list}

OR 

- [Notepad++ *Simple program to read, create or edit code*](/core-guides/tools/notepadplusplus)
{.links-list}

# Video Guides
This tutorial teaches you how to assign multiple materials to a skin properly.
A lot of the newer champions and skins require multiple materials. An indicator for that are assets, that are not always there, but for example only appear in the recall animation, like KDA Ahri’s throne. Those champions and skins also usually have more than just the basic texture in the folder Skins/base.
<br>
<div align="left">
  <a href="https://www.youtube.com/watch?v=19LhAguxJtU"><img src="https://i3.ytimg.com/vi/19LhAguxJtU/maxresdefault.jpg" alt="Guide on how to create skins with different materials"
style="width:75%"></a>
</div>

*External link to Youtube!*

---

While assigning materials you might run into a rare issue, which for example Kalista and Mordekaiser have: they have bones and materials that have the same name.
<br>

<div align="left">
  <a href="https://www.youtube.com/watch?v=Yqe_GwzF8AU"><img src="https://img.youtube.com/vi/Yqe_GwzF8AU/0.jpg" alt="Guide on how to create skins with identical materials & bones"
style="width:75%"></a>
</div>

*External link to Youtube!*

# Code Snipet
```
            MaterialOverride: list[embed] = {
                SkinMeshDataProperties_MaterialOverride {
                    Texture: string = "ASSETS/Characters/Champion/Skins/Base/TextureName.dds"
                    Submesh: string = "MeshName"
                }
            }
```
To hide meshes, you can use this! If you have multiple of them, type them out and put a space between them
```
            InitialSubmeshToHide: string = "MeshName MeshName"
```

# Writen Guide



# Sources

- Yoru Queen of Night
- ☆Guardian☆