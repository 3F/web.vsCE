---
layout: doc
title: Installation
permalink: /doc/Installation/
---

# Installation and removal 

## VSPackage

The main plugin. Contains logic for work with events of Visual Studio and core of different actions for anything.

**To install:**

 * Get latest build [{{site.lnkCur_VSPackage[1]}}]({{site.lnkCur_VSPackage[2]}}) and restart VS IDE. That's all.

If you received file with different extension: simply change on [.vsix](https://msdn.microsoft.com/en-us/library/ff407026.aspx) or install manually with command:

```{{site.msblang}}
VSIXInstaller.exe <downloaded_file>
```

**To remove:**

`VS IDE` - `Tools` - `Extension and Updates ...`: `Uninstall` or `Disable`

If you need manually:

```{{site.msblang}}
VSIXInstaller.exe /uninstall:DA5CEB32-1E09-44A5-A6AA-71D3149A53B7
```