---
layout: post
title: Announcing OpenFL 1.1 (Beta)
date: 2013-09-25 04:02:13.000000000 -07:00
---
<p>Today, we are announcing the OpenFL 1.1 beta, available now.</p>

<p>The team has been hard at work preparing for the next release, and now it is time to share with you some of the progress we have made towards the next iteration of OpenFL.</p>
<!--more--><a id="more-197"></a>

<h3>New Windowing</h3>
<p>The next version of OpenFL includes SDL 2 as a significant upgrade over the SDL 1.2 backend we used before. SDL handles the creation of windows, resizing, input events (such as mice, multi-touch, game controllers, keyboards) and other fundamental components to running on the desktop. This new version should improve the experience for desktop platforms, especially for Mac OS X, which resizes more smoothly and now has full support for 64-bit systems.</p>

<p>In addition to other hidden improvements in SDL 2, the OpenGL hardware context is now retained when resizing a window, or toggling fullscreen. If you are a developer using the OpenGLView API, this should be a welcome change.</p>

<p>Since SDL is a cornerstone to our support for Windows, Mac and Linux, we encourage you to report any feedback that you may find, particularly testing against older or more unusual systems, so we can be sure that we have not introduced any unwanted regressions by making this change.</p>
<h3>New Audio</h3>
<p>We are also introducing support for OpenAL audio on Windows, Mac, Linux and Android. We have found OpenAL to be much more resilient in testing, compared to SDL_mixer we used in the past for desktop platforms. OpenAL on Android should automatically use either lower-level Android sound APIs or OpenSL ES, depending on the version of Android. We have great expectations for continued improvements in the sound space.</p>

<p>This beta release does not streaming audio support, which should be available for the final release of OpenFL 1.1. The beta release will sounds into memory before playing. We are also interested in your feedback, comparing this new audio backend to your previous experiences, as well as any constructive input you have.</p>

<p>We are discontinuing support for the MP3 audio format (<em>for more information, please visit <a href="http://www.openfl.org/blog/2013/09/18/to-mp3-or-not-to-mp3/" target="_blank">To MP3, or not to MP3?</a>)</em></p>
<h3>Improved Assets</h3>
<p>You can read more about the improved asset library, <a href="http://www.openfl.org/blog/2013/09/12/coming-improvements-to-the-assets-library/" target="_blank">here</a>.</p>
<h3>iOS 7 and Xcode 5 Support</h3>
<p>OpenFL 1.1 offers improved support for iOS, including the new iOS 7.0 release and the Xcode 5 developer tools. In order to take advantage of the new Xcode, you will need to install a beta version of HXCPP as well.</p>

<p>By default, OpenFL will now generate launch images for you automatically, to take advantage of the full resolution of the iPhone 5. The developer tools will also handle the new iOS 7.0 icon sizes as well. If you would prefer to use your own launch images, you may do so with the "splashScreen" tag in your project file:</p>

```xml
<splashScreen path="to/image.png" width="1024" height="768" />
```

<p>We have made improvements to the deployment for iOS simulators and devices, and have added support for customize the code sign identity for your project. You may do this using a "certificate" tag in your project file:</p>

```xml
<certificate identity="iPhone Distribution" if="ios" />
```

<p>You may control the visibility of the iOS 7.0 status bar, using the "fullscreen" property of the "window" tag in your project file. The default is true for mobile platforms, but you can set it to false if you prefer to include it in your application:</p>

```xml
<window fullscreen="false" if="ios" />
```

<h3>ARMv7 Support for Android</h3>

<p>This beta release defaults to ARMv7 support on Android, instead of the older ARMv5 standard. Google does not release official statistics on the processor architecture of Android devices, but based on available information, we feel it may be time to take advantage of the minor but measurable performance boost of targeting a modern architecture.</p>

<p>If you would like to compile ARMv5 binaries for Android (which are compatible with ARMv6 and newer devices as well), you may add an "architecture" tag to your project:</p>

```bash
<architecture name="armv5" if="android" />
```

<h3>...and more</h3>

<p>There are too many improvements for us to list them all in one post. We are excited about this significant release, and continue to look forward to working together to create new and exciting content!</p>

<h3>Installation</h3>

<p>You can download the following beta versions of OpenFL libraries, here:</p>
<ul>
	<li><a href="http://www.openfl.org/files/2113/8008/1832/openfl-1.1.0-beta.zip">openfl</a></li>
	<li><a href="http://www.openfl.org/files/2013/8008/1832/openfl-tools-1.1.0-beta.zip" target="_blank">openfl-tools</a></li>
	<li><a href="http://www.openfl.org/files/2713/8008/1831/openfl-native-1.1.0-beta.zip" target="_blank">openfl-native</a></li>
	<li><a href="http://www.openfl.org/files/7613/8008/1832/openfl-html5-1.1.0-beta.zip" target="_blank">openfl-html5</a></li>
	<li><a href="http://www.openfl.org/files/7713/8008/1831/hxcpp-3.0.3-beta.zip" target="_blank">hxcpp</a></li>
</ul>
<p>After you have downloaded the ZIP packages, run:</p>

```bash
haxelib local openfl-1.1.0-beta.zip
haxelib local openfl-tools-1.1.0-beta.zip
haxelib local openfl-native-1.1.0-beta.zip
haxelib local openfl-html5-1.1.0-beta.zip
haxelib local hxcpp-3.0.3-beta.zip
```

<p>Be aware, that if you are using a development version of any of these libraries, you may need to run "haxelib dev (name of library)" to disable your development directory, or you may choose to update and rebuild whichever component you are using from the source.</p>
<h3>Feedback</h3>
<p>We welcome your feedback, and look forward to the final release!</p>
