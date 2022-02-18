---
layout: doc
title: When a file is open
permalink: /doc/Examples/TODOword/
---

# Actions when opening a file

If you want to display a dialog box when opening a file in Visual Studio if the code file contains a `TODO` comment, here's how to achieve the result,

1\. Add or activate action in main window.

2\. Add condition inside `EnvDTE` tab:

Pre | Post | Guid | Id |    | CustomIn |    | CustomOut | Cancel 
----|------|------|----|----|----------|----|-----------|--------
 &nbsp; |  ✔   | {69F5F698-996B-4293-9FE7-4202564FE6E5} | 256 |  | | | | |

3\. Activate `Script Mode` and add the following script:

```{{site.sbelang}}
#[var doc = #[DTE events.LastCommand.CustomIn]]
#[( $(doc.Length) != 0 )
{
    #[var msg = #[$([System.Text.RegularExpressions.Regex]::Matches(
        '$([System.IO.File]::ReadAllText($(doc)))', 
        "//\s*TODO.+"
    ))]]
    
    #[( $(msg.Length) != 0 )
    {
        #[File write("$(TMP)/TODO"):#[$(msg.Replace(';//', '//'))]]
        #[IO scall("notepad", "$(TMP)/TODO", 0)]
    }]
}]
```

4\. Click [Apply] button. Enjoy.

{% assign img = "examples/TODOword.png" %}{% assign attr = "width='774' height='541'" %}{% include elem/lightbox %}

Add some optional condition to filter opened or maybe closed files and their other words.

# References

* [Examples & Features](../../Examples/)
* [Processing modes](../../Modes/)
* [SobaScripts](../../Scripts/SBE-Scripts/)
* [Visual Studio Gallery page](https://visualstudiogallery.msdn.microsoft.com/ad9f19b2-04c0-46fe-9637-9a52ce4ca661/)