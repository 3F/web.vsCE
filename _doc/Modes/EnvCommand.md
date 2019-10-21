---
layout: doc
title: EnvCommand Mode
permalink: /doc/Modes/EnvCommand/
---

# EnvCommand Mode

This action type for raising of different commands for EnvDTE: [https://msdn.microsoft.com/en-us/library/EnvDTE.aspx](http://msdn.microsoft.com/en-us/library/EnvDTE.aspx)

![sample](../../Resources/examples/EnvCommand.png)

## How to use

In general, for work with EnvDTE commands you can use our sniffer tool: `Settings` - `Tools` - `EnvDTE Sniffer`

![sniffer](../../Resources/examples/CommandEvent.gif)

The `Enum` column should describe about place for this command, for example:

```text
{1496A755-94DE-11D0-8C3F-00C04FC2AAE2} 1628 Microsoft.VisualStudio.VSConstants+VSStd2KCmdID.OutputPaneComboList
```

Where:

* `Microsoft.VisualStudio.VSConstants+VSStd2KCmdID.OutputPaneComboList` tells us about operation - [OutputPaneComboList](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.vsconstants.vsstd2kcmdid.aspx?f=255&MSPPError=-2147217396)

For all this, firstly, you should use [MSDN](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.aspx) and/or listen in details our sniffer tool.

In most cases you should look first the VSStd2KCmdID & VSStd97CmdID enumerations.

### Test commands

v1.1+ is already contains the `Raise` item to check the all incoming commands inside sniffer.

![](../../Resources/examples/sniffer_raise.png)

For older versions you can use the `raise(guid, id, customIn, customOut)` method from [DTEComponent]({{site.docp}}/Scripts/SBE-Scripts/Components/DTEComponent/#method-raise) and testing tool from `Tools` - `SBE-Scripts ...`

## Pre / Post / Cancel

All raised commands will be handled in your scripts - **before** (`Pre` flag) executing by VS IDE and **after** (`Post` flag).

You can work with both variants as you want.

If you work before executing (by Visual Studio) of catched command, you can also try to **cancel** this command if needed.
For this case, you may catch and suppress any commands from Visual studio for handle **only** with your scripts *(try with `About` dlg of VS IDE, [see below](#samples))*.

## Samples

Description | Guid | Id | in | out
------------|------|----|----|----
Open the About dlg of Visual Studio |{5EFC7975-14BC-11CF-9B2B-00AA00573819} | 271 | | 
Open VS Output Window | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 237 | | 
Open VS Output Window with Item `name` | {1496A755-94DE-11D0-8C3F-00C04FC2AAE2} | 1627 | `name` | 
Close active panel | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 288 | | 
Open Solution from `path` | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 217 | `D:\App\Console1.sln` | 
Close Solution | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 219 
Select All text in editor | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 31 | | 
Cut selected text from editor | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 16 | | 
Copy selected text from editor | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 15 | | 
Paste data from buffer | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 26 | | 
Exit | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 229 | | 
Create new file `OutputLog.txt` & Open & activate in editor | {5EFC7975-14BC-11CF-9B2B-00AA00573819} | 221 | `OutputLog.txt` | 

and other...


# References

* MSDN:
    * [Microsoft.VisualStudio Namespace](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.aspx)
        * [VSStd2KCmdID](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.vsconstants.vsstd2kcmdid.aspx)
        * [VSStd97CmdID](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.vsconstants.vsstd97cmdid.aspx)
    * [EnvDTE Namespace](http://msdn.microsoft.com/en-us/library/EnvDTE.aspx)
* [Examples & Features](../../Examples/)
    * [Overriding of commands](../../Examples/Overriding/)