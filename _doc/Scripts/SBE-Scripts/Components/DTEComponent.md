---
layout: vssbedoc
title: DteComponent
description: DTE commands and events.
permalink: /doc/Scripts/SBE-Scripts/Components/DTEComponent/
---

# DteComponent

DTE commands and events.

Related to assembly-wrapped COM library containing the objects and members for Visual Studio core automation.

This component has some differences from original [vsSolutionBuildEvent](http://vssbe.r-eg.net/doc/Scripts/SBE-Scripts/Components/DTEComponent/)

## Method raise

Raise Command ID for EnvDTE.

Syntax:

```java
void raise(string guid, integer id, object customIn, object customOut)
```

Arguments:

* guid - Scope by Guid.
* id - The command ID.
* customIn - Mixed input parameters.
* customOut - Mixed output parameters.

Note:

* customIn & customOut may contain mixed data, inc. complex object as: {}, {"str", true}, {"str", {1, 2}, true}, etc.

Sample:

```java
#[DTE raise("{5EFC7975-14BC-11CF-9B2B-00AA00573819}", 271, "", {"str", {1, 'y', {-12.457f}}, true})]
```