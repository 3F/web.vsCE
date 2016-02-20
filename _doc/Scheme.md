---
layout: doc
title: Scheme of vsCommandEvent
permalink: /doc/Scheme/
---

# Scheme of vsCommandEvent

The vsCommandEvent has [more lightweight structure instead of vsSolutionBuildEvent](http://vssbe.r-eg.net/doc/Scheme/)

## Structure

{% include elem/fillme %}

## Model of events

The vsCommandEvent works on the similar Event-Actions model, i.e.:

* There is an configured event from Visual Studio.
* And exists some actions, that to be executed...

![Model of events](../Resources/events_model.png)

Basic work is a:

* Configure the event.
* Create and configure any actions for this.
* Enjoy.

# References

* [vsSolutionBuildEvent](http://vssbe.r-eg.net/doc/Scheme/)
* [Examples](../Examples/)
