---
title: Lolmaya Errorlist
description: All common and uncommon errors listed and their solutions
published: true
date: 2024-12-31T19:15:57.970Z
tags: error, fix, lolmaya
editor: markdown
dateCreated: 2024-12-31T17:38:06.431Z
---

# Lolmaya Errorlist

> Disclaimer: This list is only featuring Errors that are caused by lolmaya! If you need help with common Maya errors, please click the link below.
{.is-info}

- [Maya errorlist](/core-guides/tools/maya/errorlist)
{.links-list}

# Common Errors

## No skin cluster found
![no_skin_cluster.png](/user-pictures/bud/no_skin_cluster.png)
This error occurs when the mesh/group inside the scene is not bound with the skeleton. To fix this simply select the mesh/group and bind it together with the scene's armature in the skin -> bind skin menu.

## Mesh contains vertices that have weight on 4+ influences
![4_influences.png](/user-pictures/bud/4_influences.png)
This error occurs when the mesh that was bound to the skeleton is bound with settings allowing for vertices to have influences from more than 4 bones. League only supports up to 4 influences and you should be binding/weighting your skin around that. The easiest solution if you run into this issue is to open the LoLMaya shelf in Maya and press the button with the icon of the number 4. This will force every vertex that has 4+ influence to only 4.
<!--skibidi toilet sigma rizz-->

## Too many vertices found
![too_many_verts.png](/user-pictures/bud/too_many_verts.png)
This error occurs when the vertex count exceeds 65535. League .skn format only supports up to 16^<sup>4</sup> vertices which is 65356. The only way to resolve this error is to delete parts or decimate your mesh until it's under the limit. This error can also occur if your model has too many UVs. Around 50k UV's is the limit.