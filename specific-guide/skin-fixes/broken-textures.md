---
title: How to fix Broken textures for champions named A-J
description: A tutorial on how to fix broken textures caused by riot changing dds to tex
published: true
date: 2025-03-16T17:38:25.430Z
tags: texture, skin fix
editor: markdown
dateCreated: 2025-02-18T03:42:17.638Z
---

 # How to fix broken textures with LtMAO

> This tutorial uses LtMAO, specifically the explorer contexts. If you dont have it installed, follow the instructions [here for installing LtMAO](/core-guides/tools/LtMAO) and [here for enabling explorer contexts](/core-guides/tools/LtMAO#explorer-contexts). Alternatively, use the second section of this tutorial to fix textures without LtMAO. {.is-warning}

---

Riot is slowly changing textures to tex, causing mods to break if they have outdated dds textures. This is a tutorial on how to fix them.

## 1. Find your mod in the cslol installed folder and extract the wad.
> If you get a lot of files with random names after extracting, extract hashes first, then delete the folder and extract the wad again
{.is-info}

![ddstexwad.png](/user-pictures/fbs/ddstexwad.png)

## 2. Find your textures and convert them using LtMAO
> If your files' X and Y dimensions aren't both multiples of 4, their created tex file will crash your game or appear blank in game. 
{.is-info}

If you find any 2x, 4x files, delete them. After converting the files to tex, you can delete every dds file. If you get an error "Unsupported dds format", then convert dds to png, then png to dds and then dds to tex. U need to delete the png files just like the dds ones. If theres a particle folder, do it to every dds file there too.
![ddstexdel.png](/user-pictures/fbs/ddstexdel.png)

## 3. Repack your wad, then restart cslol.
If the wad change date changes, you can delete your folder.
![backtowad.png](/user-pictures/fbs/backtowad.png)
![deletefolder.png](/user-pictures/fbs/deletefolder.png)

This should be it. if you did everything right, your textures should look good in game.
![brad.png](/user-pictures/fbs/brad.png =x300)

---

# How to Bulk Fix WITHOUT LtMAO

> You will need both [tex2dds](https://github.com/Morilli/Ritoddstex/releases) by Morilli and [texconv](https://github.com/microsoft/DirectXTex/releases) by Microsoft. These are both small CLI utilities. It is recommended to install both of these to a folder you remember, such as "League Mod Tools".
{.is-info}

## 1. Extract your mod and it's wad file
Extract your mod's Fantome or Zip file to a folder using 7-Zip or Winrar. To add 7-Zip options to your context menu follow this guide [Fix 7-Zip Option Missing From Context Menu](https://www.intowindows.com/fix-7-zip-option-missing-from-context-menu/). Additionally, for easier access to mod files in the future, set Fantome files to open by default with 7-Zip or Winrar.

![extract_&_open.png](/user-pictures/moga/extract_&_open.png =x250)

Under your extracted folder, `Mod_Name\WAD` you will find all of your mod's files compressed within a single wad file, labeled `Champion.wad.client`. Extract this file by dragging it onto one of CSLOL's tools called `wad-extract`, found in your CSLOL directory under `CSLOL\cslol-tools\wad-extract`. This extracts your mod's files into a folder called `Champion.wad` next to your wad file.

> Similar to the technique used above to open Fantomes with 7-Zip, you can do the same for `wad.client` and `wad-extract`. Now, double clicking a wad file will extract it into a folder next to your wad.

## 2. Convert DDS to TEX in bulk without LtMAO
> Before bulk converting, it's very important to realize a few details about TEX and DDS files in league. ***As of the 25.5 patch***, 
> - Only champions who's name begin with A-J use TEX files for their textures and particles. This means AoE converting with a loop will incorrectly convert some of these files, ex. if a Caitlyn mod uses textures in a Qiyana folder. This is less common, and a more specific command can be used to work around this.
> - Most files found under `assets\shared` do not need to be TEX and should be left alone if they are.
> - ***Every*** champion, even A-J, still use DDS files for their QWER-P icons (found under `champ.wad\assets\characters\champ\hud\icons2d`).
> - ***Every*** champion uses TEX for their loadscreen, regardless of their name.

Firstly, you need to add both `tex2dds` and `texconv` to your Windows path in order to use them from within any directory, otherwise, they will only be available while inside the folder they were installed to. To do this, search `env var` from your Windows start menu and click `Edit the system environment variables` or follow this video guide since default windows search is garbage.

---

<video width="520" height="auto" controls>
  <source src="/user-pictures/moga/how_to_add_a_folder_to_path_on_windows.mp4" type="video/mp4">
</video>

Using tex2dds manually by dragging each file, from the cli like `tex2dds file.dds` to create `file.tex`, or using LtMAO's context menu is impractical.
First, navigate **inside** of your `champion.wad` folder, press `Ctrl+L` or click to focus the address bar in file explorer, type `cmd`, and press enter to open a command prompt at your current location. Your cmd path should end with `champ.wad`.

![open_cmd_here.gif](/user-pictures/moga/open_cmd_here.gif =x225)

To convert every single DDS file in a directory to TEX, or vice versa, shrimply run this for command inside `champ.wad`. Make sure you understand the four highlighted notes above.
`for /R %I in (*dds) do tex2dds "%I"` If this fails with an error or appears blank/white in game, go to step 3 and 4.
- `for` is the basic loop command used in CMD to iterate on a conditional set of files from just one command.
- `/R` is a for loop switch that indicates to loop recursively, meaning every file in every subfolder.
- `%I` represents the currently active file when looping through each file.
- `(*dds)` uses the `*` wildcard to find any file that begins with literally anything and ends in `dds`.

> Optionally, append `&& del "%I"` in order to delete your DDS file after converting to TEX.

Next, on the same command line, run `for /R %I in (4x*tex,2x*tex) do del "%I"` to delete your now redundant `4x_` and `2x_` alternative texture files. This can instead be ran first and replaced with `4x*dds,2x*dds`.

If this completed successfully, you can go to Step 5 to remake your wad file and try it in game. 

## 3. Optional: Fix bad DDS file's pixel format
> There are two requirements for a DDS file to correctly convert to a league TEX file. It must be in a DXT1, DXT5, or uncompressed BGRA8 format and it's X and Y dimensions must both be multiples of 4.
{.is-info}

This step can also be used to pre-fix any potentially bad DDS files before converting them to TEX.

In most cases, simply converting all DDS files to TEX with `tex2dds` will have worked, but if both of the above criteria aren't met, your TEX file will either simply fail to convert and produce an error such as `Error: dds file needs to be in either DXT1, DXT5 or uncompressed BGRA8 format!` or appear invisible or whited out in game.

![saved_bad_dds.png](/user-pictures/moga/saved_bad_dds.png =x200)

- Type `texconv` with no options to see all available switches.

Now, run `texconv -f BC3_UNORM -r:keep -y *dds` to iterate on all DDS files below your current directory. If you mess this up, it's ok, just delete the `Champ.wad` folder and re-extract the wad file to start over.
- `-f` is the output pixel format flag and `BC3_UNORM` is the specified format. All of the formats are listed at the bottom of the texconv help output.
- `-r` is used to tell texconv to recursively search for your input files, ie, go below your current directory, into subfolders. `:keep` leaves the output file in the same spot as it was, otherwise texconv will put every converted file into your current directory (bad!)
- `-y` overwrites your old/input file with the converted/output file.
- `*dds` uses a CMD wildcard to provide texconv with every file that begins with anything and ends in `dds`.

![img_of_texconv_cmd.png](/user-pictures/moga/img_of_texconv_cmd.png)

> It's very important you aren't in any random directory before running this because `-r` combined with the `*` wildcard will tell texconv to do **every** file under you. **If you want to work on a directory you're not inside of, you need to provide an output directory to texconv with `-o`** Ex. `texconv -f BC3_UNORM -r:keep -y -o "Mod_Name\WAD\Riven.wad" "Mod_Name\WAD\Riven.wad\*dds"`
Until you understand this command you should make sure you're under `Champ.wad` like the above image!
{.is-warning}

## 4. Optional: Fix bad DDS file's dimensions

After confirming your DDS files are in the BC3_UNORM format and converting them to TEX, they may still fail to appear as expected in game. This is uncommon, and likely because the X & Y coordinates of your DDS file were not a multiple of 4 before converting to TEX. To confirm, use [texdiag](https://github.com/microsoft/DirectXTex/releases) from the initial texconv link and run `texdiag info "file.dds"`. The output will include various information about your input file. `texdiag info -r *dds | findstr "format dds"` will search recursively and filter just the filename and format to find a bad file if there are too many potential offenders.

![texdiag_out.png](/user-pictures/moga/texdiag_out.png)

The above image is a great example of a DDS file that will not convert to TEX. Even if the format was `BC3_UNORM` tex2dds would create a TEX file that doesn't work in game because of improper dimensions.

To fix this file you need to convert the DDS' pixel format to `BC3_UNORM` as explained in Step 3, and change the dimensions to their closest multiple of 4, which in this case is `200x304`. To adjust dimensions you need to use the `-w` and `-h` switches for width and height, so `texconv -w 300 -h 304 -y "file.dds"`. If the offending file is a loadscreen, their default dimensions are `308x560`.

> Remember, if this file is not in your current directory, so if your input file is `"path\path\file.dds"` you  need to provide `-o "path\path"` before.
{.is-info}

Alternatively, use [Paint.NET](https://www.getpaint.net/index.html) to resize your DDS file in a gui application. The shortcut to open the resize window is `Ctrl+R`.

## 5. Remake wad and repack mod file

Firstly, test your fix without repacking your wad or Fantome/Zip. Simply drag the `Champ.wad` **folder** (not .client file) into CSLOL. It will work if you drag the correct folder, and it'll be called `Champion` with no metadata/description.

Once you confirm your fix is good, follow similar steps as before when you extracted your wad.
1. Drag the `Champ.wad` onto `wad-make`. This will overwrite the `Champ.wad.client` file.
2. Delete the `Champ.wad` folder.
3. Go up a directory and select both META and WAD, right click, and click "Add to archive". If this isn't available, follow this guide [Fix 7-Zip Option Missing From Context Menu](https://www.intowindows.com/fix-7-zip-option-missing-from-context-menu/).
4. Create the Zip file, and optionally rename the extension to .fantome for funsies, but CSLOL takes Zip the same as Fantome.
5. Profit.