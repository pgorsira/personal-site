---
layout: post
title:  "Home/End and Move Left/Right a Word for zsh/kitty/macOS"
date:   2018-07-20 13:31:31 -0700
categories: posts
published: false
---

Can't speak to other setups but for some reason command-left (go to beginning), command-right (go to end), option-left (go left a word), and option-right (go right a word) weren't working for me out of the box with a combination of [zsh](https://www.zsh.org/){:target="_blank"} and [kitty](https://github.com/kovidgoyal/kitty){:target="_blank"} on macOS.

Solved this by adding the following to `~/.config/kitty/kitty.conf`:

{% highlight bash %}
# move left a word
map alt+left send_text all \033b
# move right a word
map alt+right send_text all \033f
# move to beginning
map super+left send_text all \x01
# move to end
map super+right send_text all \x05
{% endhighlight %}

Restart kitty for changes to take effect.