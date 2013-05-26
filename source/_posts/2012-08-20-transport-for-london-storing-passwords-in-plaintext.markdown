---
layout: post
title: Transport for London storing passwords in plaintext
tags:
- Passwords
- UK
- Transport for London
- Cryptography
alias: /post/29832567486/transport-for-london-storing-passwords-in-plaintext
---
Yesterday while I was cleaning out my online accounts, deleted accounts and things I came across my [Photocard](https://photocard.tfl.gov.uk) login from Transport for London, I couldn't remember what this account was for so I decided to login, weirdly it said my password was incorrect, but this would have been impossible for me (unless I got hacked) because I use 1Password to generate random passwords and always store them in the app. Thinking I might have made a mistake when I saved it, I decided to do the good old "Forgot your password" procedure, entered my email and everything, and then I got the email.

When I got the email, I was amazed to see that it wasn't a link to reset my password but an actually password, I then decided to compare the password in the email and the password I saved in 1Password and then I was shocked to see that they actually emailed me my password.

![](http://media.tumblr.com/tumblr_m92ahhRh6K1qamsz8.png)

Now, you might be wondering if they emailed me my password why wasn't I able to login? Let me explain, 99% of my passwords at 16 characters, when I signed up to TfL photocard I created a 16 character password (it didn't give me an error saying it has to less than 16 characters). But the password they emailed me was 10 characters, they truncated my 16 characters password to 10. How can this be possible?

I decided to Google around to see how I can find out if passwords are being stored in plaintext, I came across this question on [Stackoverflow](http://stackoverflow.com/questions/701801/how-to-tell-if-a-site-stores-passwords-in-plain-text).

I read through all of the answers and comparing how TfL gave me my password:

  1. They managed to cut down my 16 character password to 10 and this is only possible if they stored it in plaintext I reckon.
  2. They emailed me my password in plaintext.

I am aware that this might not been they are stored in plaintext but these are very bad security practices for a **government body.**

Also TfL has multiple "minisites" which require a login, and I'm not 100% if this is the care for all of them or just this one. But, even if it is this one it is still a shambles because it contains my personal details.

NOTE: I'm not 100% sure that they are storing it in plaintext but the way the are sending me my password and somehow managed to update my passwords shows hints they might be and their security practices sucks.