---
layout: vssbedoc
title: InternalComponent
description: All internal operations with vsCE.
permalink: /doc/Scripts/SBE-Scripts/Components/InternalComponent/
---

# InternalComponent

All internal operations with vsCommandEvent.

This component has some differences from original [vsSolutionBuildEvent](http://vssbe.r-eg.net/doc/Scripts/SBE-Scripts/Components/InternalComponent/)

## Entry point for component

The vsCommandEvent requires the next name for all internal operations:

* `vsCE` or alias `Core`

Samples:

```java
#[vsCE ...]
```

```java
#[Core ...]
```