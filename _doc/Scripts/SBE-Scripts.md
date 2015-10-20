---
layout: vssbedoc
title: SBE-Scripts
permalink: /doc/Scripts/SBE-Scripts/
---

The vsCommandEvent contains same engine, however also have differences in a few components.

# Arguments

{% include elem/fillme %}

## Object type

The object type is new type for work with mixed data. It implemented special for vsCommandEvent.

Value can be from all available scalar types + complex, like this:

```java
{}
{"str", true}
{"str", {1, 'y', {-12.457f}}, true}
```
etc.

# List of avaialble components

{% include doc/SBE-Scripts/Components.html %}