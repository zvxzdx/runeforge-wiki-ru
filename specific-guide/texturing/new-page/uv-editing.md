---
title: UV Editing
description: A general overview of UV editing and modding-specific use cases of it
published: false
date: 2024-04-29T15:19:03.862Z
tags: 
editor: markdown
dateCreated: 2024-04-29T15:16:42.757Z
---

Page is still in the works, hope I get it done end of this week (5/5/24)

# Required Tools
- [Maya + LoLMaya Plugin *3D editing software*] [https://wiki.runeforge.io/en/core-guides/tools/maya]
- [Any photo editing software *`paint.net` is highly recommended*] [https://wiki.runeforge.io/en/core-guides/tools/paint-net]
{.links-list}

# Introduction to UVs
- how it works (basic level)
- importing texture files into maya for easier visualization
- UVs outside 1,1 bounding box

# Use cases in custom skins
Just a short list of possible use cases I'll be covering in this guide.
- Combining downloaded texture files into a single file
- Fixing weird UVs
- Matching added parts of a mesh

# UV editing toolbox
- LoLMaya interface
- Maya-native UV tools

# Specific use cases
## Combining downloaded texture files into a single file
This will most likely be useful if you're following [the guide for replacing champions with a different model][https://wiki.runeforge.io/en/specific-guide/3d-modelling/Replacing-Champion-With-a-Completely-Different-Model], which doesn't go into detail about how to get textures to work, but that's what this guide is for.

A champ's base texture file will be a single (or sometimes 2) square .dds file, the 2x and 4x files are the lower resolution ones. You can delete the 2x/4x ones and only replace the base one, which will also replace the lower resolution ones (they just wont be low res). (insert picture of champ's base\assets folder)

When you've downloaded a 3D model and unzip'd the .zip or .rar (or whatever file format it comes in), the extracted folder should look something like this
(insert picture of folder with textures, .fbx/.gltf, other subfolders, unneccessary files)

The only files you'll need will be texture files and the 3d model or Maya/Blender scene. There may be textures which are duplicate or have weird colour schemes.
You can delete all the files that don't look like a texture for the model (or just ignore them).

After importing the model and all texture files, the first step is figuring out what texture files belong to which part of the mesh. This is pretty easy to do just by trial-and-erroring, since it is very obvious if a texture fits a part of the mesh once you apply it (insert picture of fitting and non-fitting texture applied to a part of a mesh).

After you applied all textures to your mesh you can now delete all unused nodes in Hypershade, which will leave you with all texture files you want to combine into the champ's base texture file.

Now you can start combining the parts of the mesh that use the same texture file, which may require some UV editing.

If you're lucky, the UVs will look something like this when looked at together (insert picture of good UV)
If that's the case, you can just combine those parts of the mesh, and continue to do so until you've done this for every texture file.

If you're not lucky, it will look something like this (insert pictures of bad UVs, both single parts and multiple parts)
This is where you have to get creative and actually edit UVs