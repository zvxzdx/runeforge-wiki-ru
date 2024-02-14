---
title: LtMAO
description: A guide on how to install and use LtMAO.
published: true
date: 2024-02-14T21:58:05.194Z
tags: guide, install, ltmao
editor: markdown
dateCreated: 2024-02-11T19:27:37.139Z
---

>W.I.P.
This page is under construction and could use contribution!
{.is-warning}

# LtMAO
This page will explain the LtMAO tool made by Tarngaina and all of its features.

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
Just <a href="cslolmanager">cslol-manager</a>, but different UI.

<u style="color:orange">Important: Need to set Game folder in setting tab first to work.</u>
  
  ![cslmao.png](/user-pictures/bud/cslmao.png)
---
## leaguefile_inspector
  View League files information.
  
  ![ltmaofileinspect.png](/user-pictures/bud/ltmaofileinspect.png)
---
## animask_viewer
  Edit MaskData's weights inside animation BINs.
  
  ![animask.png](/user-pictures/bud/animask.png)
---
## hash_manager
  ![hashmanager.png](/user-pictures/bud/hashmanager.png)
  
  <u style="color:orange">Important: Please wait for all syncing/updating/loading hashes finished before process with any <kbd style="background-color:#343942;color:orange">LtMAO</kbd> functions.</u>

1. CDTB Hashes: Auto sync <a href="https://github.com/CommunityDragon/CDTB/tree/master/cdragontoolbox">CommunityDragon</a> hashes. Can also be manually downloaded at mentioned link.

 <span>
   
2. Extracted Hashes: Extract personally by user.

	<span>
    
   Hashes that can be extracted:

	- binentries:
		+ VfxSystemDefinitionData -> particlePath in BIN.
		+ StaticMaterialDef -> name in BIN.
	- binhashes:
		+ Joint hashes -> joint names in SKL.
		+ Submesh hashes -> submesh names in SKN.
	- game:
		+ File path that starts with <kbd style="background-color:#343942">assets/</kbd> or <kbd style="background-color:#343942">data/</kbd> in BIN. If file type is <a href="/e/en/core-guides/filetypes#dds">.dds</a>, extract 2x, 4x dds too.

3. Custom Hashes:

 	- Custom Hashes is hashes that used with all LtMAO related functions: leaguefile_inspector, ritobin, wad_tool,...
   
	 - Custom Hashes = CDTB Hashes + Extracted Hashes + User Manually Added Hashes


Also has generate wad & bin hash function. Those generated hashes can be added to Custom Hashes with <kbd style="background-color:#343942">-></kbd> buttons.
   
---
  ## vo_helper
Make the fantome work on all languages by cloning it.

<u style="color:orange">Important: The audio inside fantome must also come with events file to make it work on other languages.</u>
    
![vohelper.png](/user-pictures/bud/vohelper.png)
    
---
  ## no_skin
  Creates a mod that disables (almost) all riot skins and turns every champion to the default skin.
    
<kbd style="background-color:#343942">SKIPS.json</kbd>: Some skins cause League to crash when they get changed to base. This file tells the program to not change those skins to base.
  
![noskin.png](/user-pictures/bud/noskin.png)
    
  Use it by clicking "Browse Champions folder" button and locating the Champions folder inside the game installation address.
>The address should look like this: "\Riot Games\League of Legends\Game\DATA\FINAL\Champions"
>{.is-info}
  
Press the Start button and select the folder where you want the mod to be created.
  
  After the operation is completed select the .fantome file you got and put it in CsLol or cslmao.
    
 ---
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
  
  
  
  
  
  
  
  
  
  
  
  
  
  