---
layout: post
title:  "i3 Workspace Switcher for chunkwm on macOS"
date:   2018-07-13 09:22:57 -0700
categories: posts
published: false
---

Moving from Linux to macOS, I've missed tiling window managers. On Linux, I used to use [i3](https://i3wm.org/){:target="_blank"}. Recently, I found [chunkwm](https://koekeishiya.github.io/chunkwm/){:target="_blank"}, which is easily the best TWM I've used on macOS.

One thing missing from chunkwm is a nice workspace indicator / switcher like i3 has. See [here](https://fedoramagazine.org/wp-content/uploads/2016/02/i3-09-1024x768.png){:target="_blank"} in the bottom left corner for an example.

[pgorsira/chunkwm-i3-space-switcher](https://github.com/pgorsira/chunkwm-i3-space-switcher){:target="_blank"} is a menu bar widget for macOS that imitates the functionality of the i3 workspace indicator / switcher. It's a fork of [dshnkao/SpaceId](https://github.com/dshnkao/SpaceId){:target="_blank"} that shows which space is currently active and allows you to change spaces either by clicking a space number or by scrolling the mouse wheel while hovering over the widget.

To really get the best experience, you'll want to install [chunkwm-sa](https://koekeishiya.github.io/chunkwm/docs/sa.html){:target="_blank"} which allows for instant space switching (no animation). Also note that the "switching commands" are hardcoded in [NSStatusBarButton.swift](https://github.com/pgorsira/chunkwm-i3-space-switcher/blob/master/SpaceId/Application/NSStatusBarButton.swift){:target="_blank"} and you'll need to modify them if your version of chunkwm lives somewhere else. Finally, the widget is designed to really only work in `Icon Per Space` mode, so be sure to check that in the `Preferences` menu (right-click).
