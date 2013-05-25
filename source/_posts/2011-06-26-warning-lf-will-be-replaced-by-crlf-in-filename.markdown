---
layout: post
title: ! 'Warning: LF will be replaced by CRLF in FILENAME'
tags:
- git
- github
- error
- ubuntu
---
While I was pushing my current projects to Github I came across this error
"Warning: LF will be replaced by CRLF in FILENAME". It seems due to the fact
that I copied my files from Windows to Ubuntu. (More info on why this problem
occurs [here](http://stackoverflow.com/questions/1967370/git-replacing-lf-with-crlf).)

I fixed the problem by running this command:

`git config core.autocrlf false`

