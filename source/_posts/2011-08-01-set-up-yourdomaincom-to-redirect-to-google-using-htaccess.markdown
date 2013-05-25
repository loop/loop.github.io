---
layout: post
title: Set up "yourdomain.com/+" to redirect to Google+ using .htaccess
tags:
- .htaccess
- google plus
- google+
---
Create a .htaccess if you haven't already got one and add:

```
RedirectMatch ^/\+(.*)$
http://plus.google.com/YOURPLUSIDHERE$1
```

So for example Sergey Brin's would read:

```
RedirectMatch ^/\+(.*)$
http://plus.google.com/109813896768294978296$1
```

This causes http:/yourdomain.com/+ to show my posts by default but allows you
to append "about", "plusones", etc, e.g.:
[http://yourdomain.com/+/about](http://yourdomain.com/+/about) and redirect to
their respectable profile sections.

