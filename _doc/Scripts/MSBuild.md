---
layout: vssbedoc
title: MSBuild
permalink: /doc/Scripts/MSBuild/
---

{% assign infoData = "Uses [E-MSBuild](https://github.com/3F/E-MSBuild) Starting from **1.3** Part of the documentation may be irrelevant. Please update me." %}
{% include elem/info %}

## Special MSBuild Properties

List of special properties that available as MSBuild Properties.

name                 | description                                    | sample of value                                                                 | availability
---------------------|------------------------------------------------|---------------------------------------------------------------------------------|-------------
vsCommandEvent       |The version of the vsCommandEvent engine.       | 1.1.0.634                                                                       | v1.1+
vsCE_LibPath         |Full path to library.                           | C:\Users\reg\AppData\Local\Microsoft\VisualStudio\14.0\Extensions\ubnc5xvo.xia\ | v1.2+
vsCE_CommonPath      |Common path of library.                         | C:\Users\reg\Documents\Visual Studio 2015\vsCommandEvent\                       | v1.2+
vsCE_WorkPath        |Working path for library.                       | D:\prg\projects\Conari\Conari\                                                  | v1.2+

# References

* [Examples & Features](../../Examples/)
* [SBE-Scripts](../SBE-Scripts/)
* MSDN:
    * [MSBuild](http://msdn.microsoft.com/en-us/library/vstudio/dd393574.aspx)
    * [MSBuild Concepts](http://msdn.microsoft.com/en-us/library/vstudio/dd637714.aspx)
    * [Property Functions](http://msdn.microsoft.com/en-us/library/vstudio/dd633440%28v=vs.120%29.aspx)

