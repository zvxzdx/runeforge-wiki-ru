---
title: LtMAO
description: A guide on how to install and use LtMAO.
published: true
date: 2024-02-13T18:30:13.137Z
tags: guide, install, ltmao
editor: markdown
dateCreated: 2024-02-11T19:27:37.139Z
---

>W.I.P.
This page is under construction and could use contribution!
{.is-warning}

# LtMAO
This page will explain the LtMAO tool and all of its features.

---
## Download and Installation
> ### <p><span style="color:#ffffff">Installation</span>
> Download: <a href="https://github.com/tarngaina/LtMAO/archive/refs/heads/master.zip">LtMAO-master.zip</a>
> Extract: <kbd>LtMAO-master.zip</kbd>
> Run <kbd>LtMAO/start.bat</kbd>
> {.is-info}
- <a href="https://github.com/tarngaina/LtMAO?tab=readme-ov-file">LtMAO GitHub page</a>
{.links-list}
---
## cslmao
This is basically the same as <a href="cslol">CsLol</a> except the interface is a little different.
## leaguefile_inspector
  TBA
## animask_viewer
  TBA
## hash_manager
  TBA
  ## vo_helper
TBA
  ## no_skin
  This option will create a mod that disabled (almost) all riot skins and turns every champion to the default skin.
  
  Use it by clicking "Browse Champions folder" button and locating the Champions folder inside the game installation address.
>The address should look like this: "\Riot Games\League of Legends\Game\DATA\FINAL\Champions"
>{.is-info}
  
Press the Start button and select the folder where you want the mod to be created.
  
  After the operation is completed select the .fantome file you got and put it in CsLol or cslmao.
  ## uvee
  TBA
  ## shrum
  TBA
  ## hapiBin
  TBA
  ## wad_tool
  TBA
  ## pyntex
  TBA
  ## sborf
  TBA
  ## lol2fbx
  To convert .skn and .skl files to FBX simply add the .skn file with the button and the .skl will be added alongside it if it's in the same folder.
  
  Then press the skn->FBX button and you will get your FBX file.

---
  In order to convert the FBX back to .skn and .skl put the FBX in with the button and press FBX->skn.
  
  If you encounter an error in the logs look below to see what they mean and how to fix them.
  
  ---
  
  ### <span style="color:#7040F0">Possible errors when using lol2fbx
  #### <span style="color:#CF4000">IndexError: list index out of range</span>
  
  You most likely did not provide the file.
  
  ---
 #### <span style="color:#CF4000">Failed: Too many joints found
  
Your skeleton has a bigger number of joints than supported, 256.
  
  ---
  #### <span style="color:#CF4000">Exception: lol2fbx: Failed: body contains vertices shared by multiple material.
  
  The mesh contains vertices that are shared by multiple materials, this needs to be fixed in Maya or Blender.
  
  ---
  
   #### <span style="color:#CF4000"> ValueError: min() arg is an empty sequence
  Editor bud encountered this error but has no idea what it is or how to fix it.
  
  Assumption is that something is wrong with the FBX file.
  
  ---
  <!--ADD MORE INFO :PRAY:-->
  <!--ADD LINKS TO STUFF FOR THE LOVE OF GOD-->
  
  
  
  
  
  
  
  
  
  
  
  
  
  