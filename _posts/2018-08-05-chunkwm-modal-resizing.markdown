---
layout: post
title:  "Distinct Resize Mode for chunkwm Windows"
date:   2018-08-05 18:26:55 -0700
categories: posts
published: false
---

In [i3](https://i3wm.org/){:target="_blank"}, window resizing is handled by entering a specific resizing mode, making the sizing changes desired, and then exiting that mode. 

I wanted to emulate that arrangement with my [chunkwm](https://koekeishiya.github.io/chunkwm/){:target="_blank"} setup on macOS. I use [skhd](https://github.com/koekeishiya/skhd){:target="_blank"} to translate keyboard shortcuts into chunkwm actions; if you use something else this is not going to work.

Add the following to your `~/.skhdrc`:

{% highlight bash %}
# add an on_enter command to the default mode
:: default : chunkc border::color 0xff0f6288

# defines a new mode 'resize' with an on_enter command, that captures keypresses
:: resize @ : chunkc border::color 0xff24ccaa

# from 'default' mode, activate mode 'resize'
# (this is the key combination you want to use to enter resize mode)
ctrl - r ; resize  

# from 'resize' mode, activate mode 'default'
# (this is the keypress required to leave resize mode)
resize < escape ; default

# resize window in different directions
# (i'm using hjkl but you could just as easily use arrow keys, wasd, etc.)
resize < h : chunkc tiling::window --use-temporary-ratio 0.05 --adjust-window-edge west; chunkc tiling::window --use-temporary-ratio -0.05 --adjust-window-edge east;
resize < j : chunkc tiling::window --use-temporary-ratio 0.05 --adjust-window-edge south; chunkc tiling::window --use-temporary-ratio -0.05 --adjust-window-edge north;
resize < k : chunkc tiling::window --use-temporary-ratio 0.05 --adjust-window-edge north; chunkc tiling::window --use-temporary-ratio -0.05 --adjust-window-edge south;
resize < l : chunkc tiling::window --use-temporary-ratio 0.05 --adjust-window-edge east; chunkc tiling::window --use-temporary-ratio -0.05 --adjust-window-edge west;
{% endhighlight %}
