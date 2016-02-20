---
layout: vssbedoc
title: OWPComponent
description: Works with OWP and similar operations.
permalink: /doc/Scripts/SBE-Scripts/Components/OWPComponent/
---

# OWPComponent

For work with OWP (Output Window Pane) and similar operations.

This component has some differences from original [vsSolutionBuildEvent](http://vssbe.r-eg.net/doc/Scripts/SBE-Scripts/Components/OWPComponent/)

## log

Provides data from events of logging.

`Has been disabled for vsCommandEvent version`


## out

For streaming of getting the mixed data from selected pane.

Syntax:

```{{site.sbelang}}
#[OWP out(string ident [, boolean isGuid])]
```

Arguments:

* ident - Name of pane.
* isGuid - Optional flag to use Guid as identifier if true, otherwise as name of item. [MSDN. Guids of Output Pane](https://msdn.microsoft.com/en-us/library/bb166496.aspx?f=255&MSPPError=-2147217396#Anchor_4)
    * BuildOrder: `2032b126-7c8d-48ad-8026-0e0348004fc0`
    * BuildOutput: `1BD8A850-02D1-11d1-BEE7-00A0C913D1F8`
    * DebugOutput: `FC076020-078A-11D1-A7DF-00A0C9110051`
    * [...](https://msdn.microsoft.com/en-us/library/bb166496.aspx?f=255&MSPPError=-2147217396#Anchor_4)

Sample:

```{{site.sbelang}}
#[OWP out("Build")]
```

Note: The "Build" item is used by default with property `out` as alias:

```{{site.sbelang}}
#[OWP out]
```

Also used as short alias for: `out.All`