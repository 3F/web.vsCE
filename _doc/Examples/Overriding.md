---
layout: doc
title: Overriding of commands
permalink: /doc/Examples/Overriding/
---

# Overriding of commands

![Overriding](../../Resources/examples/cmds/ill.png)

The all environment of any users may be flexibly changed as you want for different cases...

This possible because the vsCommandEvent **may override a lot of commands** from Visual Studio, 
and due to the fact that it is based on [vsSolutionBuildEvent](http://vssbe.r-eg.net) engine, it also provides a many [flexible actions](../../Examples/) as you need...

## How to

Let's consider a simple example.

How about to override the 'Exit' (including `Alt + F4` hotkey) form Visual Studio IDE ?

![Exit command](../../Resources/examples/cmds/menu.png)

And how about of next actions below instead of original exit:

* Copy all data from VS Output Window.
* Then create new text file, open and activate it.
* Finally - Paste the log data from VS Output Window.
* And supress termination of Visual Studio IDE.

ok, **it's simply**:

* Add new action and select `EnvDTE` tab.
* Add next condition:

 Guid | Id | in | out | Cancel | Pre | Post
------|----|----|-----|--------|-----|-----
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 229 | | | v | v | 

Then select `EnvCommand Mode`[^1] and add next commands:

 Guid | Id | in | out 
------|----|----|-----
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 237 | | 
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 31 | | 
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 15 | | 
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 221 | OutputLog.txt | 
{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 26 | | 

* Activate event and click [Apply]. Enjoy.

![](../../Resources/examples/cmds/live.gif)

**Note:** the example above is used simple EnvDTE commands as action type.
However, the vsCommandEvent **also** provides different engines for complex scripting if needed - [SBE-Scripts](../../Scripts/SBE-Scripts/), [MSBuild](../../Scripts/MSBuild/), [C#](../../Modes/CSharp/) and [others ...](../../Modes/)

# References

* [Examples & Features](../../Examples/)
* [Automatic Version Numbering](../Version number/)
* [Processing modes](../../Modes/)
* [SBE-Scripts](../../Scripts/SBE-Scripts/)
* [Visual Studio Gallery page](https://visualstudiogallery.msdn.microsoft.com/ad9f19b2-04c0-46fe-9637-9a52ce4ca661/)

[^1]: For more details about EnvCommand Mode - you should use [this page](../../Modes/EnvCommand/)