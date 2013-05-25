---
layout: post
title: Posterous For iPad
tags:
- Posterous
- iPad
- Apps
- How to
---
I recently got an iPad 2 and it seems I can do a lot of stuff from it! The
only things I use my desktop is for programming and work things. I use
Posterous for some stuff and it seems there is no iPad app for it! It is very
weird as the founder used to be an Apple employee and has "never owned a PC".

I found a simple way to install their multi-functional bookmarket on the
Safari bookmark bar. It is really simple:

1. Add this page to your bookmark bar.
2. Then edit the bookmark and rename it to what ever you like, I renamed it to "Posterous"; nice and simple.
3. Then copy and paste the code below into the URL section.
```
  javascript:var b=document.body;var POSTEROUS___bookmarklet_domain='http://posterous.com';var d=new Date();var e=(new Date(d.getFullYear(),d.getMonth(),d.getDate())).getTime();if(b&&!document.xmlVersion){void(z=document.createElement('script'));void(z.type='text/javascript');void(z.src='http://posterous.com/javascripts/bookmarklet2.js?'+e);void(b.appendChild(z));}else{}
```

You are now done.

Update 25-May-2013: I've been going through all my posts to make sure everything was mirgated correctly from Tumblr and I should point out this post is now useless. Posterous has been acquired by Twitter and been shut down.