
# FE8 Skill System

[Main discussion on Fire Emblem Universe](https://feuniverse.us/t/fe8-skill-system-v1-0-254-skills-done-more-on-the-way/2312)

## What is this?

This is a fully-functional system for implementing modern FE skills into Fire
Emblem 8.

This repository is intended to be installed via Event Assembler. Other methods
of installation, such as FEBuilderGBA, are not officially supported.

## 改变

1.移除了ups生成工具，full模式下的补丁生成命令。因为差分补丁过程中，修改后的ROM内容消失了。或许是我电脑原因。

2.把贝里克物语回合制加了进来(credit to Stan，他是这个模式的作者)

3.移除了测试地图，编译后相当于在原本基础上加了技能系统和LTF(就是指2，Stan的叫法)

## 自定义

1.修改`LazberianTurnFlow/LazberianTurnFlow.event` 里面的gLTFChapterEnableList:可以指定章节使用LTF模式，(指定章节id开启)，默认加入了全部id，即全开

2.修改`ROMBuildfile.event` 里面，BWS上面三块，控制技能系统，BWS控制贝里克回合制。其他适用于EventAssembler的也可以加进来。按需求增删。(记得把下面Installion里的Event Assembler11.0.1解压进来)

## Installation

1. Get the latest version of Event Assembler (v11.0.1 as of this release) and put it in the extracted folder.
2. Get a clean FE8U ROM, name it "FE8_clean.gba" and put it in the extracted folder.
3. Run MAKE HACK_full when you make text or table changes. If you aren't inserting new text or tables, you can use MAKE HACK_quick instead.

## Basic Usage Notes

- Only 254 skills can be used at a time. To configure which skills are in use, use `Engine Hacks\Skill System\skill_definitions.event`. This also doubles as a list of all skills and their effects.
- Several optional toggles for other assembly hacks (such as the STR/MAG split, save expansion, etc) as well as the configuration of the effects of various skills can be found in `Engine Hacks\Config.event`.
- To customize skill learnsets (what skills learned, at what level), see `Engine Hacks\Skill System\Skill_lists.event`.
- To customize things like personal skills, class skills, and other miscellaneous things, see the CSVs in `Tables\FE8 Nightmare modules`.

## I found a bug! What can I do about it?

Check out our [issue tracker](https://github.com/FireEmblemUniverse/SkillSystem_FE8/issues) on Github.

## Credits

See `CREDITS.md` for a more detailed list.

Special thanks go to:
  - Circleseverywhere, for creating and releasing the original system.
  - Crazycolorz5, for debuffs, freeze and Dragon's Veins.
  - Primefusion, for the test map.
  - Kirb, for implementing the Str/Mag split into FE8 based off Tequila's original FE7 version.

