---
title: Basic Information
description: Basic Information to do SFX modding!
published: true
date: 2024-02-13T19:08:00.499Z
tags: sfx, audio, voice over, sound effects, sound, effect, vo
editor: markdown
dateCreated: 2024-02-10T20:41:38.554Z
---

# Sound Effects
## Point 1: Basic information.
League of Legends, like many games, have a complex yet effective system to compress files that makes the game posible to run. Specificaly in the audio system, there are many layers of compression being made. To access the neat files of the game we have to follow some instructions (go to point 4 to skip all the information).
## Point 2: Formats of files.
For sound modding in League of Legends we use these type of files:
- **.wad.client**: Combination of compressed files that is used to hold multiple files at once (not only used for sounds (every mod for a champion changs some of these files)). For sound modding, this compression system is what holds **Champions Sound Effects**. There is a variation of these files that has a language prefix before ".wad" (**en_US.wad.client**; *en_US* being the prefix for the english language) that is used to contain every **Voice Line** for the champion in that specific language.
Here is a list of every prefix used and their respective language.
> ja_JP: Japanese
ko_KR: Korean
zh_CN: Chinese
zh_TW: Taiwanese
es_ES: Spanish (Spain)
es_MX: Spanish (Mexico)
en_US: English (USA)
en_GB: English (Great Britain)
en_AU: English (Australia)
fr_FR: French
de_DE: German
it_IT: Italian
pl_PL: Polish
ro_RO: Romanian
el_GR: Greek
pt_BR: Portuguese
hu_HU: Hungarian
ru_RU: Russian
tr_TR: Turkish

> To see any of this game files you have to have downloaded that version of the game (in the Riot Client go to settings and change the language for League of Legends. select and download the version that you want and go into a game)
{.is-warning}

- .wav: Generic audio file format used before converting into the format that League of Legends can read.
- .wem: File format that the game reads. You can not use any other type of audio format to replace sounds
- .bin: Code that reads every .wem file and makes the logic to get it to work in game; something like the brain of the game. (Not only used for sounds)
- .bnk: Format that contains all the compressed .wem files that a model can have. There are two distinctions of the formats: "events.bnk" and "audio.bnk"