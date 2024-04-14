---
title: Understanding and Using Shaders
description: A guide about using StaticMaterialDef in riot bins
published: false
date: 2024-04-14T21:34:14.317Z
tags: 
editor: markdown
dateCreated: 2024-04-14T21:34:14.317Z
---

# Overview
In League of Legends there are some types of shaders, some for Environment, PostProcessing, and the one we use for our custom models SkinnedMesh.
To simplify Shaders can be characterized as effects that are applied in the 3D Model (The Submesh).
**Shaders doesn't follow any pattern**, some uses masks with multiple color channels, another ones doesn't have masks, so you need to analyze the original implementation of the shader that you are wanting to edit/copy.

# Important notes on StaticMaterialDef
* Each **submesh** can only handle **one** shader.
* Avoid using the same name when using multiple materials, it can lead to one of them not loading.