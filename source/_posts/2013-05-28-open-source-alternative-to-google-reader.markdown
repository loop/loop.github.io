---
layout: post
title: "Open Source Alternative to Google Reader"
date: 2013-05-29 13:09
comments: true
categories:
- Google Reader
- Tiny Tiny RSS
- Heroku
- Open Source
- RSS Reader
published: true
---
As you may know [Google Reader](http://www.google.com/reader) will be shutting down on [1st July](http://googlereader.blogspot.co.uk/2013/03/powering-down-google-reader.html) and I've spent quite some time looking at alternatives to replace it. I've been using Google Reader since 2009, I've read over 100,000 (from the web app) items and starred/shared over 2000 of them. I had a nice little setup going.

Google Reader was amazing, it had some amazing third-party apps like [Reeder](http://reederapp.com/), it had a full array of features (the most important one was speed!) which made it the best RSS Reader out there. I used and abandoned a few alternatives, these ranged from using [Twitter as a replacementt](http://blog.capwatkins.com/switching-from-rss-to-twitter), [Feedly](http://www.feedly.com/), [The Old Reader](http://theoldreader.com/) and [NewsBlur](http://www.newsblur.com/). All these alternatives had pitfalls. Twitter was annoying because it required switching between my accounts and it was very annoying to use. Another thing that I had set up was any starred articles I did on Google Reader, they would automatically get bookmarked into [Pinboard](http://pinboard.in) using [ifttt](https://ifttt.com), it used to be possible but it was [removed](http://thenextweb.com/apps/2012/09/20/ifttt-removes-twitter-triggers-comply-new-api-policies/) due to Twitters API changes. The rest of the services I tried were either slow, provided too many features for me to care about or didn't have an API or apps.

I wanted a reader that was simple, not bloated with features and did everything that Google Reader did. [Tiny Tiny RSS](http://tt-rss.org/) did all of that, best of all it was open source and self hosted. It was simple and had plug-ins which you can install or develop your self.

I couldn't install this on my server due to some constraints so I decided to look at [Heroku](https://www.heroku.com/). I came across a script called [ttrss-on-heroku](https://github.com/projectdelphai/ttrss-on-heroku) and he was trying to do the exact same thing as me. I used the script and got TTRSS set up with in 5 minutes and have been using it for the past 3 weeks and it has been working perfectly. The feeds get updated every 5 minutes and the cost of this set up on Heroku is 0. I recommend you read up on how exactly this works from the script developers post [here](http://projectdelphai.github.io/blog/2013/03/23/tt-rss-on-heroku-part-2/).

I've installed [TTRSS-Reader](https://play.google.com/store/apps/details?id=org.ttrssreader) on my Android, while it isn't pretty to look at, it does the job.
If you have a iOS device, you might want to install Reeder[^1], you can use that with TTRSS. All you need to do is install the [plug-in](http://tt-rss.org/forum/viewtopic.php?f=22&t=1981).

To have that Google Reader elements, I installed the following plug ins:

- [Google Reader theme](http://tt-rss.org/forum/viewtopic.php?f=22&t=1574)
- [Google Reader keyboard shortcuts](http://tt-rss.org/forum/viewtopic.php?f=22&t=1363)
- [Video frames](https://github.com/tribut/ttrss-videoframes), this embeds videos into TTRSS.

Another thing, I had to setup was starred articles to Pinboard. I used ifttt for this. In the **Special** folder there is a subsection called **Starred**, you can actually view this as a RSS feed, by clicking on the RSS icon on the top right-hand side. With this you should get something like this:

`http://myrssreader.herokuapp.com/public.php?op=rss&id=-1&key=2cd209as34df3451eedef139cba4b19d10ee6158`

With that feed URL, you can set up a ifttt recipe that takes the RSS feed and adds any new posts to your Pinboard.

This is my full setup to replace Google Reader and has been working well so far. Heroku is awesome for making available the free plan and hope they never remove this, and [Andrew Dolgov](http://tt-rss.org/redmine/users/4) is awesome for developing TTRSS.

[^1]: The Fever integration is currently only available to iPhone, but is coming to rest of the devices soon as [tweeted](https://twitter.com/reederapp/status/317003560963407872) by the developer.