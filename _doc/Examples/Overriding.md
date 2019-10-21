---
layout: doc
title: Overriding of commands
permalink: /doc/Examples/Overriding/
---

# Overriding of commands

![Overriding](../../Resources/examples/cmds/ill.png)

The dev environment of any users may be flexibly changed as you need in a few steps.

This is possible because vsCommandEvent **may override a lot of things** from Visual Studio, and it also provides [flexible actions](../../Examples/) due to the fact that it was based on [vsSolutionBuildEvent](https://github.com/3F/vsSolutionBuildEvent). 

![About dlg](../../Resources/examples/AboutVS.gif)

## How to

vsCommandEvent provides various modes to process your custom scripts. From shell commands to C# code, from [E-MSBuild](https://github.com/3F/E-MSBuild) to [SobaScript](https://github.com/3F/SobaScript), and more.

But let's consider only EnvDTE commands. Because you can even override the 'Exit' (including [X] and Alt + F4 hotkey) on the fly 🔧 without code. Just native EnvDTE commands for everything in your mind.

![Exit command](../../Resources/examples/cmds/menu.png)

For example, the following actions are also possible for native EnvDTE commands:

* Copy all data from VS Output Window.
* Then create new text file, open and activate it.
* Finally - Paste the log data from VS Output Window.
* And supress termination of Visual Studio IDE.

**Please note:** *Of course you can do it via other available processing modes (scripts support with E-MSBuild, SobaScript, C#, etc.). Just example for pure EnvDTE commands.*

1. Add new action and select `EnvDTE` tab.
2. Add next condition:

 Guid | Id | in | out | Cancel | Pre | Post
------|----|----|-----|--------|-----|-----
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 229 | | | v | v | 

3.Then select `EnvCommand Mode`[^1] and add next commands:

 Guid | Id | in | out 
------|----|----|-----
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 237 | | 
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 31 | | 
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 15 | | 
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 221 | OutputLog.txt | 
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 26 | | 

4.Activate event and click [Apply]. Enjoy.

![](../../Resources/examples/cmds/live.gif)

Optional scripts are possible through [**other** modes](../../Modes/): [C#](../../Modes/CSharp/), [SBE-Scripts](../../Scripts/SBE-Scripts/), [MSBuild](../../Scripts/MSBuild/)

# References

* [Examples & Features](../../Examples/)
* [Automatic Version Numbering](../Version number/)
* [Processing modes](../../Modes/)
* [SBE-Scripts](../../Scripts/SBE-Scripts/)
* [Visual Studio Gallery page](https://visualstudiogallery.msdn.microsoft.com/ad9f19b2-04c0-46fe-9637-9a52ce4ca661/)

[^1]: For more details about EnvCommand Mode, read [this page](../../Modes/EnvCommand/)