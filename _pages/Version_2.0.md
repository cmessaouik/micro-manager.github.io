---
autogenerated: true
title: Version 2.0
layout: page
section: Version 2.0
---

Micro-Manager 2.0 is a major step forwards compared to the 1.4 series
that preceded it. The user interface (UI) has been overhauled,
especially with respect to the image display window. The API has also
been completely reworked, allowing for more powerful scripts and
plugins. This was all enabled by a new internal data model for working
with images and image metadata.

This page serves as a "hub" for various other pages related to Version
2.0.

### Downloads

2.0 development now takes place in the "master" branch on github.

Nightly builds:
[Windows](http://valelab.ucsf.edu/~MM/nightlyBuilds/2.0.0-gamma/Windows/)
\| [Mac OS
X](http://valelab.ucsf.edu/~MM/nightlyBuilds/2.0.0-gamma/Mac/)  
Source code [in master branch on
github](http://github.com/micro-manager/micro-manager/tree/master)

### Contributing to MM2.0

[How to debug and develop
MM2.0](How_to_debug_and_develop_MM2.0 "wikilink")

### API

If you want to write a new plugin or script, you will need to
familiarize yourself with the new API.
[Version\_2.0\_API](Version_2.0_API "wikilink") has an overview of the
API's capabilities. Plugin authors should also read
[Version\_2.0\_Plugins](Version_2.0_Plugins "wikilink").

[Version\_2.0\_API\_How\_do\_I](Version_2.0_API_How_do_I "wikilink") is
a demonstration of how to accomplish various common tasks using the new
API. If you have a task that you want to perform that is not covered,
then please ask us on the mailing list and we can update the
documentation.

[Version\_2.0\_API\_Transition\_Guide](Version_2.0_API_Transition_Guide "wikilink")
is a transition guide to help people who are familiar with the 1.4 API
and need to port their code to the 2.0 API. It breaks down where old API
methods have gone and how to replace deprecated methods.

The [Javadocs](http://valelab.ucsf.edu/~MM/doc-2.0.0-beta2/mmstudio/)
will likely also prove useful. All packages whose names do \_not\_
include "internal" are part of the API in 2.0. In particular, the [root
API](http://valelab.ucsf.edu/~MM/doc-2.0.0-beta2/mmstudio/),
[data](http://valelab.ucsf.edu/~MM/doc-2.0.0-beta2/mmstudio/org/micromanager/data/package-summary.html),
and [display](http://valelab.ucsf.edu/~MM/doc-2.0.0-beta2/mmstudio/)
packages should prove useful.

### API Events

Version 2.0 provides greater access to the event publication and
subscription system initially introduced in 1.4.
[Version\_2.0\_API\_Events](Version_2.0_API_Events "wikilink") has more
information on what events are available.

### Other Documentation

For some examples of writing Beanshell scripts for 2.0, see
[Version\_2.0\_Scripts](Version_2.0_Scripts "wikilink")

Version 2.0 includes a new User Profile system; see
[Version\_2.0\_Profiles](Version_2.0_Profiles "wikilink") for more
information.
