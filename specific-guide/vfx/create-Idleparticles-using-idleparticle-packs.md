---
title: Create Idleparticles
description: This is a guide explaining how to create idle particles using the custom-made idle particle packs.
published: true
date: 2024-05-08T05:01:51.431Z
tags: #idleparticles
editor: markdown
dateCreated: 2024-05-08T04:44:42.696Z
---

# Required tools



- [Obsidian *Click here*](https://wiki.runeforge.io/en/core-guides/tools/obsidian)
- [CSLOL MANAGER *Click here*](https://wiki.runeforge.io/en/core-guides/tools/cslolmanager)
- [RITOBIN *Click here*](https://wiki.runeforge.io/en/core-guides/tools/rito-bin)
- [Any Code editor *Click here*](https://wiki.runeforge.io/en/core-guides/tools#code-bin-editing)
{.links-list}




# For what is this guide?

This is a guide explaining how to create idle particles using the custom-made idle particle packs.
This !Guide! will not show you how to create idle particles by your own.
It will only guide you on how to copy and paste custom-made idle particle packs into your champ. wad.client

# What are idleparticles?

They are also known as "Auras".

IdleParticlesEffects is an emitter in the main.bin of your champ, which tells the game which particles you set as idle particles (auras).


# Is it difficult to make idle particles?

It's not that hard if you just copy and paste idle particle packs that are specially prebuilt, like these ones.
Locating them and changing them to become idle particles is the difficult part. Even still, copying and pasting these lines of code into one's own code can be difficult. Especially if you have 0 experience.
So keep patient and follow the steps 1 by 1.
If there is any error, you did something wrong, and you should check if you placed the brackets and lines correctly.
# Written Guide

Look at the bottom of the page to find a video guide and the downloads.

0. Download an idle particle pack, which you can find at the bottom of the page.

---

1. Open Obsidian and extract the champ files you want into a folder with whatever name you want.

---
2. Open the champ folder and the folder you downloaded, and paste the customparticles folder, which is in assets, into your assets folder.

![step_2.png](/user-pictures/friendlyfrog/step_2.png)

---
3. Now go to your champions folder again and go to thefolderyoumade\data\characters\yourchamp\skins and convert the skin0.bin to .py by just dragging it onto ritobin_cli.exe.


Also open the .py file, which is in the idleparticle folder you downloaded.

Ritobin_cli.exe needs to be in the folder it was originally in with the hashes folder. Otherwise, you will have many hashed code names, like 0x3s4d5e5.

---
4. Open both files with Visual Studio Code.
   Paste this code from the idleparticle folder you downloaded into your skin0.bin/.py
   Keep the position of the code in your mind and try to reproduce the steps.
![step_4.1.png](/user-pictures/friendlyfrog/step_4.1.png)

effectKey: hash = is the link to the particlecontainer

boneName: string = is the bone you want the idleparticle applied to

Bones you can use:

"Spine1" = Spine middle of the body

"Head" = Head top of the body

"L_Hand" or "R_Hand" = hands 

"Pelvis" = pelvis

"R_Foot" or "L_Foot" = Feets

"C_Buffbone_Glb_Layout_Loc" = A not moving bone which is located on the floor.
                              Use this bone to have a stationary idle particle.

"Weapon" = Probably the weapon bone. You should look into the skeleton (.skl) of the champ to find out.
Since many champs have different weapon bone names.

---

5. Copy the particlecontainer code, which always starts with a hashed (0x3432432) name and ends with particlePath: string, into your skin0.bin/.py. Just between any particle container, it doesn't matter between which one.


Keep in mind that if the skin.bin has no particles in it, you need to paste it in between mResourceResolver: link = "Characters/Shaco/Skins/Skin0/Resources" and "Characters/yourchamp/Skins/Skin0/Resources" = ResourceResolver. *look bottom of tutorial for picture.

![step5.1.png](/user-pictures/friendlyfrog/step5.1.png)
![step5.2.png](/user-pictures/friendlyfrog/step5.2.png)

---

 6. Copy and paste the code found in the character resolver into your bin. Just between anything doesn't matter.


![step_6_2.png](/user-pictures/friendlyfrog/step_6_2.png)


![step_6_2.png](/user-pictures/friendlyfrog/step_6_2.png)

---
7. Save the file by going into the top left corner clicking file and save.

---
8.  Drag your skin0.py onto ritobin_cli.exe again and see if the time and date change. If it doesn't change, there is an error, and you need to repeat my steps.

---
9. Drag the folder that you created at the beginning into CSLOL and look in-game to see if the idle particles got applied.

---
  *picture from step 5 if you have no particles in your bin.

![extra_step.png](/user-pictures/friendlyfrog/extra_step.png)

# Video Guide

<div align="left">
  <a href="https://www.youtube.com/watch?v=lfW8YBAUJHw"><img src="https://img.youtube.com/vi/lfW8YBAUJHw/0.jpg" alt="Guide on how to create idle particles"
style="width:75%"></a>
</div>

# Idle particle packs

BRAND HAND FLAMES AURA

![brand_aura.gif](/user-pictures/friendlyfrog/brand_aura.gif)

https://drive.google.com/file/d/1RbwSYwkhUI0M-s42vuqX5kVCBM_xXxDV/view?usp=drive_link

---
Udyr E AURA AND SMOKE

![udyr_e_aura.gif](/user-pictures/friendlyfrog/udyr_e_aura.gif)

---
GLOW AURA AND SETT BASIC ATTACK TRAILS 

0x84809410 = Hand trails

0x6047adf7 = Glow

https://drive.google.com/file/d/1ucKyVonQdo_-Ww3rtGMM2It08X1fP4OL/view?usp=drive_link

![udyr_glow_and_sett_ba_trail.gif](/user-pictures/friendlyfrog/udyr_glow_and_sett_ba_trail.gif)

---
SWAIN+YONE AURA

0x42e58c6a = Swain's part of the aura

0x78882b8c = Yone's part of the aura

https://drive.google.com/file/d/1oFVwb23Trf3h0utjXRXOPnWSZ0rB8OMj/view?usp=drive_link


![swain+yone_aura.gif](/user-pictures/friendlyfrog/swain+yone_aura.gif)


https://drive.google.com/file/d/1Ynxe4eCPq8cqLf31efsZmnKO7brl-n0F/view?usp=drive_link

---
SETT ELECTRICTY AURA 

![electricity_aura.gif](/user-pictures/friendlyfrog/electricity_aura.gif)

https://drive.google.com/file/d/167oKE-0yLm7lKgzkC9zam-Coz9Y2ryIG/view?usp=drive_link

---

EZREAL BATTLE ACADEMIA PASSIVE AURA

![ezreal_battle_academia_passive_aura.gif](/user-pictures/friendlyfrog/ezreal_battle_academia_passive_aura.gif)

https://drive.google.com/file/d/11O3miLODy9_YJ6Y1ACkOEe6BjgwEBcqj/view?usp=drive_link


---
SPIRIT BLOSSOM AURA

![spirit_blossom_aura.gif](/user-pictures/friendlyfrog/spirit_blossom_aura.gif)

https://drive.google.com/file/d/1oeiVDS7QnQHtuotMJiyQgD4_boMElH42/view?usp=drive_link

---
STAR GUARDIAN AURA

![star_guardian_stars.gif](/user-pictures/friendlyfrog/star_guardian_stars.gif)

https://drive.google.com/file/d/1wEOlaMaE9B8WNSghgMOZn2-AvUhU2MM2/view?usp=drive_link


---
RIVEN SPIRIT BLOSSOM R SWORD AURA

![riven_r_word_aura.gif](/user-pictures/friendlyfrog/riven_r_word_aura.gif)

https://drive.google.com/file/d/1nxt3Wiz0c-6GYe4M4CYM9e4FiFIeV36V/view?usp=drive_link


# THE END

I hope you like my guide, and I'm open for criticism.

Guide made by FriendlyFrog

If you want to contact me, type me on Discord or visit the official RuneForge Discord.

Also, if anyone collects auras, send them to me; I will separate them and repath the files.

I will add more auras to this guide and collect more of them.

Runeforge Discord: https://discord.com/invite/runeforgenvite/runeforge

Discord: friendzoned6843