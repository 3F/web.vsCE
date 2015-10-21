---
layout: vssbedoc
title: Solution-wide Build Events
permalink: /doc/Features/Solution-wide/
---

Yes, it's also possible for vsCommandEvent, it means - why not...

## How to

The vsCommandEvent may work with commands from VS, so you can catch command when started the Build or Rebuild, Clean etc. for all solution as for all projects at once or similar... 

**However**, it cannot be same for [vsSolutionBuildEvent](http://vssbe.r-eg.net), because he work on [another technologies](http://vssbe.r-eg.net/doc/Scheme/).

[Here](../../Modes/EnvCommand/), you will know more about how to work with commands, and for this case you should configure EnvDTE tab, for example:

Description | Guid | Id | in | out
------------|------|----|----|----
Started - Build Solution |{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 882 | | 
Started - Rebuild Solution |{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 883 | | 
Started - Clean Solution |{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 885 | | 

You can **also suppress** all this operations, for example, allowing the Build operation only for some cases (with [SBE-Scripts](../../Scripts/SBE-Scripts/), [C# Mode](../../Modes/CSharp/)) etc.

## What's exists for work without plugins ?

If you need a very simple variant without any additions, see [here](http://vssbe.r-eg.net/doc/Features/Solution-wide/#what-39-s-exists-for-work-without-plugins)