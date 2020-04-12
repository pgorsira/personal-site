---
layout: post
title:  "Removing Firefox's Title Bar"
date:   2018-07-26 15:12:42 -0700
categories: posts
published: false
---

Be sure that `Title Bar` is unchecked in the `Customize Toolbar...` menu. Tested on macOS only, but presumably should work elsewhere.

Add the following to userChrome.css:

{% highlight css %}
#main-window #titlebar {
    display: none !important;
}
#nav-bar{
    margin-top: -20px;
}
#TabsToolbar{
    height: 0;
}
{% endhighlight %}

Will have to restart Firefox to see changes.