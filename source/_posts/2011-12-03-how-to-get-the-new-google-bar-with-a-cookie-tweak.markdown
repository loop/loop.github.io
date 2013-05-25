---
layout: post
title: How To Get The New Google Bar With A Cookie Tweak
tags:
- Cookie Tweak
- Design
- Google Bar
- Google Chrome
- IE
- Safari
- UI
- Opera
---
I've seen a blog [post](http://feeds.gawker.com/~r/lifehacker/vip/~3/28C0NJYiwYc/get-the-new-google-bar-now-with-a-cookie-tweak) on Lifehacker about getting the new [Google Bar](http://googleblog.blogspot.com/2011/11/next-stage-in-our-redesign.html). It has some pointless shit on installing a Google Chrome extension, that is really unnecessary! You can just do it via the console on the browser.

<strike>This only seems to work for google.com domain as it is rolling out onthat site first.</strike>

It works on all google domains. I was being stupid and not reading the code properly. In the little bit of code that you copy and paste change **.google.com** to your Google, so I would change it to **.google.co.uk** and follow the other steps as usual. It works on ALL Google!

To enable the new Google Bar on Google Chrome:

  1. Press **Shift + Ctrl + J**.
  2. Copy and paste 
```
document.cookie="PREF=ID=03fd476a699d6487:U=88e8716486ff1e5d:FF=0:LD=en:CR=2:TM=1322688084:LM=1322688085:S=McEsyvcXKMiVfGds; path=/; domain=.google.com";window.location.reload();
```

To enable the new Google Bar on Firefox:

  1. Press **Ctrl + Shift + K**.
  2. Copy and paste 
```
document.cookie="PREF=ID=03fd476a699d6487:U=88e8716486ff1e5d:FF=0:LD=en:CR=2:TM=1322688084:LM=1322688085:S=McEsyvcXKMiVfGds; path=/; domain=.google.com";window.location.reload();
```

To enable the new Google Bar on Internet Explorer:

  1. Press **F12**.
  2. Click the **Console** tab.
  3. Copy and paste 
```
document.cookie="PREF=ID=03fd476a699d6487:U=88e8716486ff1e5d:FF=0:LD=en:CR=2:TM=1322688084:LM=1322688085:S=McEsyvcXKMiVfGds; path=/; domain=.google.com";window.location.reload();
```

To enable the new Google Bar on Safari:

  1. Press **Ctrl + ,**.
  2. Click **Advanced** tab.
  3. Check "**Show Develop in menu bar**".
  4. Close window.
  5. Press **Ctrl + Alt + C**.
  6. Copy and paste 
```
document.cookie="PREF=ID=03fd476a699d6487:U=88e8716486ff1e5d:FF=0:LD=en:CR=2:TM=1322688084:LM=1322688085:S=McEsyvcXKMiVfGds; path=/; domain=.google.com";window.location.reload();
```

To enable the new Google Bar on Opera:

  1. It just doesn't work so slap your self for downloading this browser.

_Note: As [ryandvm](http://hackerne.ws/item?id=3308026) of HackerNews posted, it doesn't work for Google Apps account yet._

