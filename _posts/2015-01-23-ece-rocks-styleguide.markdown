---
layout: post
title:  "ece rocks styleguide"
date:   2015-01-23 17:30:00
author: Alex Kersten
categories: alex admin
---

Alright, up and running. We're going to see how well we can apply open-source to blogging. Specifically, this entire blog is just a [Jekyll][jekyll]-powered static site [waiting for pull requests][github]. I'm sure we're not the first, but we're gonna try this pattern out and see how it fits.

The first project I'll post here will be the script to periodically fetch the latest commit and rebuild the blog. Maybe that'll just wind up being a simple cronjob, but we'll see.

This first post will also kind of serve as a style guide to replace the Jekyll boilerplate one. Posts use a flavor of markdown called [kramdown][kramdown] which allows for some simple but elegant formatting.

---

Horizontal rules separate sections of a post. Code callouts look like `this` and there's some other cool things we can do as well like syntax highlighting:

{% highlight python %}
wisdom_of_the_ancients = str(...)
print(wisdom_of_the_ancients)
{% endhighlight %}

Program output:

> Blockquotes are pretty much the best.

---

There are a few guidelines to follow when posting here:

1. Make sure to tag your posts with categories including your contributor name, so we can easily see who wrote what.
    1. I mean currently this is just our first names, if we start getting collisions we'll probably start adding tildes, accents, and unicode characters to make us really stand out.
    2. Also establishing few basic categories would be good, but really if we follow the convention that we list our names on our articles first, you're actually free to clutter up your directory with however many categories you want - but consistency would be nice (e.g. use `alex ece` rather than `ece alex` to set the category, as the first creates `/alex/ece/` in the URL which is preferred).
2. Make good use of visuals.
3. Don't break the build.

---

Tables are pretty handy, so let's demo them.

| Left-aligned | Centered | Right-aligned |
|:-            |:-:       |-:             |
| Left thing   | Center   | Right thing   |

---

Images are an essential visual aid and it would be remiss of me not to sample one here. This is a picture of light diffracted off of a CD and projected onto the bottom of a graphics card, where it is only visible on the PCB traces and creates an awesome pattern. It is one of my favorite photos that I've ever taken[^1].

![Cool PCB]({{ site.url }}/assets/img/sample_picture.jpg)


[^1]: I may be biased.

[jekyll]:      http://jekyllrb.com
[github]:	http://github.com/akersten/ece-rocks
[kramdown]:	http://kramdown.gettalong.org
[kramdownref]:	http://kramdown.gettalong.org/quickref.html
