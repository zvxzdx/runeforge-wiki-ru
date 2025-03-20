---
title: Fix Broken textures for champions with names starting with A-J
description: A tutorial on how to fix broken textures caused by riot changing DDS to TEX
published: true
date: 2025-03-20T05:51:54.998Z
tags: texture, skin fix
editor: markdown
dateCreated: 2025-02-18T03:42:17.638Z
---

> The first section of this tutorial uses LtMAO, specifically its explorer contexts. Follow the instructions [here to install LtMAO](/core-guides/tools/LtMAO) and [here for enabling explorer contexts](/core-guides/tools/LtMAO#explorer-contexts).
> 
> Alternatively, use the [second section of this tutorial](https://wiki.runeforge.io/en/specific-guide/skin-fixes/broken-textures#bulk-fix-large-mods-no-ltmao) to fix textures without LtMAO. {.is-warning}

Riot is in the process of updating League's main texture file format from DDS to TEX, updating groups of champions in alphabetical order. This causes mods to break because Riot's files are now looking for TEX files while your mod still includes DDS files.

---

# Update Textures With LtMAO

## 1. Extract WAD from CSLOL installed folder

Find your mod's WAD file under CSLOL's installed folder at `CSLOL\installed\Mod_Name\WAD`.

![ltmao_unpack.png](/user-pictures/moga/ltmao_unpack.png =x320)

## 2. Locate texture files and convert DDS to TEX

1. First, you can delete alternate files, ie., files beginning with `4x_` or `2x_` because TEX does not need alternate files to display at lower texture settings.
2. Convert each DDS file to TEX by right clicking it, selecting `LtMAO` then click `Ritoddstex: Convert To TEX`.
3. After you convert your files to TEX, you can delete any remaining DDS files. If LtMAO gives any errors like `Unsupported DDS format`, try converting to PNG using the same context menu, back to DDS, and finally to TEX. You can delete your remaining PNG files alongside the DDS files.
4. If theres a folder labeled `particles`, you need to convert DDS files there as well.

![ddstexdel.png](/user-pictures/fbs/ddstexdel.png)

## 3. Repack your WAD and reload CSLOL

![backtowad.png](/user-pictures/fbs/backtowad.png)
![deletefolder.png](/user-pictures/fbs/deletefolder.png)

This should be it. If you did everything right, your textures should look normal again in game.

![brad.png](/user-pictures/fbs/brad.png =x300)

---

# Bulk Fix Large Mods (No LtMAO)

> You will need both [tex2dds](https://github.com/Morilli/Ritoddstex/releases) by Morilli and [texconv](https://github.com/microsoft/DirectXTex/releases) by Microsoft. These are both small CLI utilities. Install both of these to a folder you can remember later.
{.is-info}

This tutorial uses CMD, but you can use Powershell if you want, you just need to adjust the commands quite a bit as loops arent similar and some tools are not the same as in CMD. Also, to use env vars in Powershell you need to append `$env:` ex., `%pbe%` is `$env:pbe` in Powershell.

## 1. Extract your mod and it's WAD file
Extract your mod's Fantome or Zip file to a folder using 7-Zip or Winrar. To add 7-Zip options to your context menu follow this guide [Fix 7-Zip Option Missing From Context Menu](https://www.intowindows.com/fix-7-zip-option-missing-from-context-menu/). Additionally, for easier access to your mod's files in the future, set Fantome files to open by default with 7-Zip or Winrar.

![extract_&_open.png](/user-pictures/moga/extract_&_open.png =x250)

Under your extracted folder, `Mod_Name\WAD` you will find all of your mod's files compressed within a single WAD file, labeled `Champion.wad.client` or `Champion.en_US.wad.client`. Extract a WAD by dragging it onto one of CSLOL's tools called `wad-extract`, found in your CSLOL directory under `CSLOL\cslol-tools\wad-extract`. This extracts your mod's files into a folder called `Champion.wad` next to your WAD file. It may be necessary to have updated hashes and their full pathnames in your `wad-extract` directory, although some files may be custom or no known hash regardless. Unknown hashes will not prevent you from converting or editing your files, but without them you may inadvertantly edit files, such as any QWER+P icons because they are largely indistingushable while not in their directory.

> Similar to the technique used above to open Fantomes with 7-Zip, you can do the same for WAD files with the extension `.client` and `wad-extract`. Now, double clicking a WAD file has `wad-extract` extract it into a folder next to your WAD.

## 2. Convert DDS to TEX in bulk without LtMAO
> Before bulk converting, it is very important to realize a few details about TEX and DDS files in league. ***As of the 25.5 patch***, 
> - Only champions who's name begin with A-J use TEX files for their textures and particles. This means AoE converting with a loop will incorrectly convert some of these files, ex. if a Caitlyn mod uses textures in a Qiyana folder. This is less common, and a more specific command can be used to work around this.
> - Most files found under `assets\shared` do not need to be TEX and should be left alone if they are.
> - ***Every*** champion, even A-J, still uses DDS files for their QWER-P icons (found under `champ.wad\assets\characters\champ\hud\icons2d`).
> - ***Every*** champion uses TEX for their loadscreen and ingame profile pictures, regardless of their name.

Firstly, you need to add both `tex2dds` and `texconv` to your Windows path in order to use them from within any directory, otherwise, they will only be available while inside the folder they were installed to. To do this, search `env var` from your Windows start menu and click `Edit the system environment variables` or follow this video guide since default windows search is garbage.

---

<video width="720" height="auto" controls>
  <source src="/user-pictures/moga/how_to_add_a_folder_to_path_on_windows.mp4" type="video/mp4">
</video>

Using tex2dds manually by dragging each file, from the cli like `tex2dds file.dds` to create `file.tex`, or using LtMAO's context menu is impractical.
First, navigate **inside** of your `champion.wad` folder, press `Ctrl+L` or click to focus the address bar in file explorer, type `cmd`, and press enter to open a command prompt at your current location. Your cmd path should end with `champ.wad`.

![open_cmd_here.gif](/user-pictures/moga/open_cmd_here.gif =x225)

To convert every single DDS file in a directory to TEX, or vice versa, shrimply run this for command inside `champ.wad`. Make sure you understand the four highlighted notes above.
`for /R %I in (*dds) do tex2dds "%I"` If this fails with an error, appears blank/white in game, or wont load and crashes, see step 3 and 4.
- `for` is the basic loop command used in CMD to iterate on a conditional set of files from just one command.
- `/R` is a for loop switch that indicates to loop recursively, meaning every file in every subfolder.
- `%I` represents the currently active file when looping through each file.
- `(*dds)` uses the `*` wildcard to find any file that begins with literally anything and ends in `dds`.

> Optionally, append `&& del "%I"` in order to delete your DDS file after converting to TEX.

Next, on the same command line, run `for /R %I in (4x*tex,2x*tex,4x*dds,2x*dds) do del "%I"` to delete your now redundant `4x_` and `2x_` alternative texture files.

If this completed successfully, you can go to Step 5 to remake your WAD file and try it in game. 

## 3. Optional: Fix bad DDS pixel format
> There are two requirements for a DDS file to correctly convert to a league TEX file. It must be in a DXT1, DXT5, or uncompressed BGRA8 format and it's X and Y dimensions must both be multiples of 4.
{.is-info}

This step can also be used to pre-fix any potentially bad DDS files before converting them to TEX.

In most cases, simply converting all DDS files to TEX with `tex2dds` will have worked, but if both of the above criteria are not met, your TEX file will either simply fail to convert and produce an error such as `Error: dds file needs to be in either DXT1, DXT5 or uncompressed BGRA8 format!`, appear invisible or whited out in game, or fail to load and crash League.

![saved_bad_dds.png](/user-pictures/moga/saved_bad_dds.png =x200)

- Type `texconv` with no options to see all available switches.

Now, run `texconv -f BC3_UNORM -r:keep -y *dds` to iterate on all DDS files below your current directory. If you mess this up, just delete the `Champ.wad` folder and re-extract the WAD file to start over.
- `-f` is the output pixel format flag and `BC3_UNORM` is the specified format. All of the formats are listed at the bottom of the texconv help output.
- `-r` is used to tell texconv to recursively search for your input files, ie, go below your current directory, into subfolders. `:keep` leaves the output file in the same spot as it was, otherwise texconv will put every converted file into your current directory (bad!)
- `-y` overwrites your old/input file with the converted/output file.
- `*dds` uses a CMD wildcard to provide texconv with every file that begins with anything and ends in `dds`.

![img_of_texconv_cmd.png](/user-pictures/moga/img_of_texconv_cmd.png)

> It is also important you are not in any random directory before running this because `-r` combined with the `*` wildcard will tell texconv to do **every** file under you. **If you want to work on a directory you are not inside of, you need to provide an output directory to texconv with `-o`** Ex. `texconv -f BC3_UNORM -r:keep -y -o "Mod_Name\WAD\Riven.wad" "Mod_Name\WAD\Riven.wad\*dds"`
Until you understand this command you should make sure you are under `Champ.wad` like the above image!
{.is-warning}

## 4. Optional: Fix bad DDS file's dimensions

This section is slightly more nuanced and may seem confusing, but in the end it is 1-2 commands and little reading.

After confirming your DDS files are in the BC3_UNORM format and converting them to TEX, they may still fail to appear as expected in game. This is uncommon, and is because the X & Y coordinates of your DDS file were not a multiple of 4 before converting to TEX. To confirm this, use [texdiag](https://github.com/microsoft/DirectXTex/releases) from the initial texconv link and run `texdiag info "file.dds"`. The output will include various information about your input file.

![texdiag_out.png](/user-pictures/moga/texdiag_out.png)

The above image is a great example of a DDS file that will not convert to TEX. Even if the format was `BC3_UNORM` tex2dds would create a TEX file that does not work in game because of it's improper dimensions.

To fix this file you need to convert the DDS' pixel format to `BC3_UNORM` as explained in Step 3, and change the dimensions to their closest multiple of 4. To adjust dimensions, use the `-w` and `-h` switches for width and height, so `texconv -w 300 -h 304 -y "file.dds"`. If the offending file is a loadscreen, their default dimensions are `308x560`.

> Remember, if this file is not in your current directory, so if your input file is `"path\path\file.dds"` you need to provide `-o "path\path"` before.
{.is-info}

If you are unable to find the broken file(s) manually there is simple way to find them.
1. Run `texdiag info -r *dds>>%desktop%\all.txt`, into a text file. Note `%desktop%` is an example path, change that directory and filename to one for your drive.
2. Next, do `texdiag info -r *dds | findstr "width height">>%desktop%\sizes.txt` which uses FINDSTR to filter just the lines including width and height information.
3. Open `sizes.txt` and remove any duplicate lines using `Ctrl+Shift+D` if using Notepad++. This leaves you with a list of each unique dimension from every DDS file.

![npp_sizes.png](/user-pictures/moga/npp_sizes.png)

As you can see from this list of dimensions, there are two values that are not multiples of 4. Using this information you can go to `all.txt` and search for 1534 to find the files with incorrect dimensions.

This is just an underdeveloped shortcut to finding bad files. With better filters and some conditionals you could easily make something that prints out offending files instead of finding them manually.

Alternatively, you can use [Paint.NET](https://www.getpaint.net/index.html) to resize your DDS file in a gui application. The shortcut to open the resize window is `Ctrl+R`.

## 5. Remake WAD and repack mod file

Firstly, test your fix without repacking your WAD or Fantome/Zip. Simply drag the `Champ.wad` **folder** (not .client file) into CSLOL. It will load normally if you drag the correct folder, and it's name will be `Champion` with no metadata or description information.

Once you confirm your fix works as expected, follow similar steps as before when you extracted your WAD.
1. Drag the `Champ.wad` onto `wad-make`. This will overwrite the `Champ.wad.client` file.
2. Delete the `Champ.wad` folder.
3. Go up a directory, select both META and WAD, right click, and click "Add to archive". If this is not available, follow this guide [Fix 7-Zip Option Missing From Context Menu](https://www.intowindows.com/fix-7-zip-option-missing-from-context-menu/).
You can also use 7-Zip from CMD assuming it's part of your PATH. To make a structurally correct mod use `7z a "Mod_Name.zip" META WAD RAW` while inside the directory with those folders leaving you with a zip file as your mod next to your WAD/META/RAW folders. You need to know exactly where you are when you run this or make the zip manually because if you nest or otherwise make an incorrect mod structure, upon importing the mod into CSLOL it will simply error out.
4. After you have successfully made your Zip file, *and optionally rename the extension to .fantome for fun*, you can use your mod in CSLOL. A Fantome file is a Zip file with additional information about the file, and is unncessary at all.
5. Profit.