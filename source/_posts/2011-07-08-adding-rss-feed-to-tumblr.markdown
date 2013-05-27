---
layout: post
title: Adding RSS Feed To Tumblr
tags:
- RSS Feed
- Tumblr
- HTML
alias: /post/7384985958/adding-rss-feed-to-tumblr
---
I noticed that some themes on Tumblr don't have option to enable RSS feed for
your blog and thought it was Tumblr's fault, well it is not. You can enable
RSS feed for your blog your self by enabling custom theme and adding the
following code anywhere between `<head>` and `</head>`, best to add it at the top
along with the other meta data.

Code is:

``` html
<link rel="alternate" type="application/rss+xml" title="RSS" href="http://yourdomain.com/rss"/>
```

Note: Make sure you change yourdomain to your Tumblr URL or if you are using
custom URL to that one.

