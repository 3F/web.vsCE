---
layout: vssbedoc
title: Stop build on first error
permalink: /doc/Examples/Errors.Stop build/
---

# Stop build on first error

The vsCommandEvent also contains this feature and you should use **[this documentation](http://vssbe.r-eg.net/doc/Examples/Errors.Stop%20build/)**, however with next notice:

Instead of "Errors-Build" event, you should configure the `Output window` tab:


variant  | Guid                                    | Item   | Condition                            | Type
---------|-----------------------------------------|---------|-------------------------------------|------
№ 1     |`{1BD8A850-02D1-11d1-BEE7-00A0C913D1F8}` |         | <code>\s+error\s+([&#94;:]+):</code> | Regexp
№ 2     |                                         | `Build` | <code>\s+error\s+([&#94;:]+):</code> | Regexp


if you need control of errors and warnings, use for example:

Condition | Type
----------|------
<code>\s+(?:error&#124;warning)\s+([&#94;:]+):</code> | Regexp

## How to get this error/warning

If also need getting of this data, you should use [SBE-Scripts](../../Scripts/SBE-Scripts/) engine, for example:

```{{site.sbelang1}}
#[( #[OWP out.Warnings.Count] > 0 ){
    ... #[OWP out.Warnings.Codes]
}]

...
#[OWP out.Errors]
```

see [OWPComponent](../../Scripts/SBE-Scripts/Components/OWPComponent/) for details.


# References

* [Examples & Features](../../Examples/)
* [Processing modes](../../Modes/)
* [SBE-Scripts](../../Scripts/SBE-Scripts/)
    * [OWPComponent](../../Scripts/SBE-Scripts/Components/OWPComponent/)
* [Visual Studio Gallery page](https://visualstudiogallery.msdn.microsoft.com/ad9f19b2-04c0-46fe-9637-9a52ce4ca661/)
