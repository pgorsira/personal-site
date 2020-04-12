---
layout: post
title:  "Forcing Monochrome Emojis in Firefox"
date:   2018-08-01 10:10:28 -0700
categories: posts
published: false
---

Before                     |  After 
:-------------------------:|:-------------------------:
![](/assets/images/before_firefox_emoji.png)  |  ![](/assets/images/after_firefox_emoji.png)

First, install the Symbola font from [this page](http://users.teilar.gr/~g1951d/){:target="_blank"}.

To handle cases where Emoji font is unspecified by page, open `about:config` and set `font.name-list.emoji` to `Symbola`.

However, in most cases, pages will specify a font when displaying Emoji. To handle this, install the [Emoji to English](https://addons.mozilla.org/en-US/firefox/addon/emoji-to-english/){:target="_blank"} addon. In the addon preferences, set the following configuration:

- Translation display: `Hide translation`
- Show emoji: `Yes`

Then add the following user style with an addon like [Stylus](https://addons.mozilla.org/en-US/firefox/addon/styl-us/){:target="_blank"} or by just inserting the CSS into your `userContent.css` file:

{% highlight css %}
.emoji-to-english-translatable{
    font-family: "Symbola";
}
{% endhighlight %}