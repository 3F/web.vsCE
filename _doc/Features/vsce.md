---
layout: doc
title: .vsce File
permalink: /doc/Features/.vsce/
---

# .vsce

The vsCommandEvent also uses the [JSON format](http://json.org) (text-based language-independent data interchange format)

## Where it placed ?

It should be 2 places below:

### Common .vsce

The common settings for all your Visual Studio should stored in:

`%HOMEPATH%\Documents\` -> `Visual Studio <num>\vsCommandEvent` directory. Where `<num>` is version of used Visual Studio.

For example: `C:\Users\<user>\Documents\Visual Studio 2013\vsCommandEvent\.vsce`

### .vsce for Solution

Optional, your settings may stored with specific solution. For this case, all configuration can be shared for other users.

You can manage of this in `Settings` - `Configuration`:

* Enable `Use Solution context` if need storing configuration in solution folder.
* Disable `Use Solution context` if need ignoring of already existing shared configuration from other users etc.
* Use `Clone from ... config` for a quick copying of configuration between Common & Solution context.

You can also ignore the .vsce from repo with scm if need ([.gitignore](http://git-scm.com/docs/gitignore), .hgignore, .bzrignore, svn:ignore, etc.,)

## .vsce for each .sln (Solution File)

You can also define the special version of configuration file for specific solution (for example).

`<SolutionFile>.vsce`

Sample:

If you have a different solution files:

* app_2012.sln
* app_2013.sln
etc.

you can also define specific configuration like this:

* app_2012.vsce
* app_2013.vsce
etc.

The specific configuration in the priority if the **.vsce** used along with **[SolutionFile].vsce**. 

## .vsce.user

The `.vsce.user` is a user configuration (for specific user).

We strongly recommend to ignore this from your SCM, 
because this contains settings e.g.: 
value of zooming & Word wrapping of main editor, DebugMode & CacheData of binaries for [C# Mode](../../Modes/CSharp/), etc.
