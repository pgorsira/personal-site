---
layout: post
title:  "Scroll to Change Volume in macOS Menu Bar"
date:   2018-07-20 19:41:03 -0700
categories: posts
published: false
---

Some operating systems allow you to change system volume my scrolling your mouse wheel over the icon in the system tray. I wanted to reproduce this effect on macOS.

There are existing utilities that do this like [VolumeScroll](http://www.volumescroll.com/){:target="_blank"} but 1) its "scroll area" is the entire menu bar instead of a specific volume icon and 2) it's not open source.

[pgorsira/volume](https://github.com/pgorsira/volume){:target="_blank"} runs in your menu bar and allows scrolling up or down with mouse wheel to change volume. It's a fork of [yene/volume](https://github.com/yene/volume){:target="_blank"} which brings the vertical volume slider back to the menu bar. Note that it's built with mouse wheel scrolling in mind and will produce undesirable results when scrolled with the touchpad.

You can right-click the icon while running and configure it to run at startup. I'd also recommend unchecking `Show volume in menu bar` in macOS sound preferences to avoid having two volume icons. 