---
layout: vssbedoc
title: SBE-Scripts
permalink: /doc/Scripts/SBE-Scripts/
---

{% assign infoData = "Uses [SobaScript](https://github.com/3F/SobaScript) Starting from **1.3.** Part of the documentation may be irrelevant. Please update me." %}
{% include elem/info %}

Togehter with [MSBuild](../MSBuild/) provides and powerful conditions, subcommands, file operations, and lot of other.

---- 

The vsCommandEvent contains the same engine, but also has differences in several components.

## Arguments

{% include elem/fillme %}

### Object type

The object type is new type for work with complex mixed data. It implemented special for vsCommandEvent.

Value can be from all available scalar types + complex, like this:

```java
{}
{"str", true}
{"str", {1, 'y', {-12.457f}}, true}
```
etc.

## List of avaialble components

Currently the most of the components are similar to original from [vsSolutionBuildEvent](http://vssbe.r-eg.net/doc/Scripts/SBE-Scripts/)

The documentation [here](http://vssbe.r-eg.net/doc/Scripts/SBE-Scripts/Components/)

### The differences

{% assign infoData = "Please see a [list of changes](/Changelist/#vssbe) for checking the actual state of availability of components and some differences between both engines." %}
{% include elem/info %}

List of components that have some differences from original:

{% include doc/SBE-Scripts/Components.html %}