---
layout: post
title:  "generated at birth"
date:   2015-02-01 02:00:00
author: Alex Kersten
categories: alex
---

Imagine a system that houses your most important data and through which you
make your most vital fiscal decisions. A platform via which you can borrow
 against credit, relinquish power of attorney, receive government benefits, and
 command financial accounts. Surely such a platform would be routinely audited
 for security - a single compromise of user credentials would prove devastating
  to the unfortunate victims. Surely users would be held to the utmost
  standards of password hygiene, with complexity enforcement and mandatory
  two-factor authentication. Surely, if such a system's security were to be
  measured by the yardstick, and an impregnable utopia were the goalposts, we'd
   at least be in the redzone?

You'd better grab your napkins, because we're way back in the nosebleeds. In
a different stadium.

Astute readers may have noticed that at least the functional description of
our hypothetical platform does reflect a real system in the US - we have a
central identity system through which we can perform all of the
aforementioned tasks and more. The only trouble is the way we authenticate
our identity with this platform. Or, more specifically, the fact that *we
can't*.

> *Developer A:* Hey, I just committed the finishing touches for our new online
banking login portal. Tell me what you think, yeah?

> *Dev B:* This looks great and all, but where's the password field? I can only
type in my username.

> *Dev A:* Your username _is_ the password!

Of course, I'm talking about social security numbers. We entrust our
reputation to the enduring secrecy of a 9-digit number. A 9-digit number
 whose keyspace is continuously shrinking[^1], whose components can be
 predicted[^2], and whose secrecy for millions of individuals has been
 obliterated countless times over by accidental release[^3] and compromise of
  completely auxiliary services[^4].

Clearly, the system is fundamentally flawed. Let's go back to the drawing
board and look at the problem we're trying to solve. We need a way to provide
 a proof of identify iff we truly are the person identified by that identity.
  That is, we need a system where simply having a signature from a person
 cannot be used to generate more signatures or signatures in a different
 context.

Sound familiar? It should, because this is a solved problem. In fact, it has
been solved so many times that there is an entire field of mathematics
devoted to it. We're talking about [public-key cryptography](http://en
.wikipedia.org/wiki/Public-key_cryptography). Let's take this for a spin.

Imagine that, at birth, you are generated[^5] a keypair.

That concept is powerful enough to be its own paragraph. Take your keypair
and sign revocable subkeys with it. Use a subkey to sign whatever dreadful
contract your local monopolistic ISP cooks up. When you're done with their
service, revoke the key by signing a dated revocation notice with it, and
whatever credit authority is responsible for computing your credit score will
 not honor credit adjustments after a key has been revoked. In contrast to
 the present-day system where myriad people have had their credit destroyed
 by false accusations of unreturned equipment or breach of contract.

An individual can be identified by their signature, and they now have complete
control over their identity. A secret number that is thousands of bytes long
is a lot harder to lose than a 9-digit number that you give away.


 [^1]: [SSN Death Master File](http://ssdmf.info/)
 [^2]: [SSN prefixes by state](http://www.ssa.gov/employer/stateweb.htm). By
 the way, [SSN randomization](http://www.ssa.gov/employer/randomization.html)
  is about as useful as trying to extend the longevity of the IPv4 address
  space, and is also not relevant to you (unless you were born after June 2011)
 [^3]: [SSNs released premortem](http://cancelthesefunerals.com/)
 [^4]: Why does my ISP need to know my SSN?
 [^5]: Through some secure air-gapped hardware RNG, offloaded onto
 read-only time-locked media, and entrusted to your guardian until you are
 of-age to make independent decisions


So why do we trust the authentication of our identities to the
secrecy of a single id?




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
