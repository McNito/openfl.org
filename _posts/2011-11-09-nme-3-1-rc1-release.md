---
layout: post
title: NME 3.1 RC1 Release
date: 2011-11-09 22:43:41.000000000 -08:00
---
The next release is here: NME 3.1 RC1 is available for download on the <a href="http://www.haxenme.org/developers/get-started">Get Started page</a>.

In addition to the new features and stability improvements from previous releases, RC1 (most notably) adds two exciting improvements:
<ul>
	<li>drawTiles now supports scale, alpha, RGB and smoothing</li>
	<li>"nme setup" will automate the install for supporting tools</li>
</ul>
NME uses OpenGL to render for most targets. In order to improve rendering performance, you can use the drawTiles API to send a batch draw command to OpenGL at once. In addition to the position and ID of the tile to draw, you can now support image batches with unique scale, alpha or RGB for each tile.

One of NME's greatest strengths is that it relies on the standard tools for each platform. This improves compile times, runtime performance and makes it easier to customize your builds. However, it can be difficult to get all the tools in place, especially for Android.

This release improves the command-line tools significantly. First, you can call "nme setup" to install a script so you don't have to type "haxelib run" to access NME anymore:

```bash
haxelib run nme setup
```

Then you can use "nme setup (target)" to automatically download, install and configure the tools required to use one of NME's targets. For example:

```bash
nme setup webos
Download and install the HP webOS SDK? [y/n/a] ? y
Downloading HP_webOS_SDK-Win-3.0.4-669-x64.exe...
8739050/283305624 (3%)
```

The "setup" command is available for Windows, Mac and Linux, for all targets except for Flash.
