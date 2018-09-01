---
layout: post
title: "Frontend Optimization Checklist 2018"
date: 2018-07-23 22:19:11 -0500
excerpt: a checklist to make your website faster
comments: true
categories: development
tags: code development optimization frontend
---
Today I wanted to write down a collective list of things you can do on the frontend to save all of the **kbs** (or **mbs** 🤔).

First off, if you have not heard of Google's [Lighthouse](https://developers.google.com/web/tools/lighthouse/) plugin yet, head on over and [download it](https://chrome.google.com/webstore/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk). This will help you understand where your website needs improvement.

I will break things down into sections:

* [SVGs & Images](#svgs-images)
* [CSS & Javascript](#css-javascript)
* [Fonts](#fonts)
* [Video](#video)
* [Server Side](#server-side)

## SVGs & Images {#svgs-images}

***

***Use of Inline SVGs*** - If you are not using SVGs for icons/logos/pretty much anything other than an actual photo, you should start doing so. Inline SVG is taking things a step further, instead of referencing a SVG in an `<img>`, inline it! This cuts down on so many asset requests on your page, for example:

{% highlight html %}
<!-- 3 extra requests -->
<img src="/extra/request/blue-circle.png">
<img src="/extra/request/yellow-circle.png">
<img src="/extra/request/red-circle.png">
{% endhighlight %}


{% highlight html %}
<!-- 0 extra requests -->
<svg height="100" width="100">
  <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="blue" />
</svg>
<svg height="100" width="100">
  <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="yellow" />
</svg>
<svg height="100" width="100">
  <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
</svg>
{% endhighlight %}

***Optimize SVGs*** - [svgomg](https://jakearchibald.github.io/svgomg/)

***Resizing image*** - Always make sure the image you are serving up is cropped / sized down to the smallest size it will ever display as. With the responsive approach and max-widths of markup containers, this can sometimes be overlooked.

***Image Compression*** - [TinyPNG](https://tinypng.com) Mac users swear by [imageoptim](https://imageoptim.com/mac)

## CSS & Javascript {#css-javascript}

***

***PurgeCSS*** -

***Minification*** -

***GZip*** -

[Difference between Minification and GZipping](https://css-tricks.com/the-difference-between-minification-and-gzipping/)

## Fonts {#fonts}

***

## Video {#video}

***

## Server Side {#server-side}

***

***HTTP/2*** - Wherever you are serving up your files on the server, make sure they are using the faster HTTP/2 protocol instead of the HTTP/1.1 protocol. To test if you are, run Lighthouse on the desired site.

On apache servers, the use of the modules for file serving/expiration/caching: **mod_headers**, **mod_expires** and **mod_deflate**
Take a look at my `.htaccess` file on [github](https://github.com/calebnance/jekyll_blog-calebnance/blob/master/.htaccess) for help.

***

This post was mainly in response to this [Twitter Post](https://twitter.com/chriscoyier/status/1030488369199906816) from [Chris Coyier](https://twitter.com/chriscoyier). I hope it helped!
