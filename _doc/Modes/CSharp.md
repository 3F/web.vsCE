---
layout: vssbedoc
title: C# Mode
permalink: /doc/Modes/CSharp/
---

# C# Mode

This action type for work with C# compiler - feel free with all events & actions.

The vsCommandEvent has some differences from original [engine](http://vssbe.r-eg.net/doc/Modes/CSharp/)

## Default Entry point

```csharp
using ICommand = net.r_eg.vsCE.Actions.ICommand;
using ISolutionEvent = net.r_eg.vsCE.Events.ISolutionEvent;

namespace vsCommandEvent
{
    public class CSharpMode
    {
        public static int Init(ICommand cmd, ISolutionEvent evt)
        {
            return 0;
        }
    }
}
```