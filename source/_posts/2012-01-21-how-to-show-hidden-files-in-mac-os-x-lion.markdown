---
layout: post
title: How to show hidden files in Mac OS X Lion
tags:
- Mac OS X
- GitHub
- Terminal
- Tips
- Hidden Files
- Finder
alias: /post/16224627186/how-to-show-hidden-files-in-mac-os-x-lion
---
I recently got a MacBook Pro and am still setting it up. I recently ran into the annoying .DS_Store files while committing to GitHub. I decided to create .gitignore and it seems there isn't a easy way to make hidden files visible other than doing it via Terminal. The steps to make hidden files visible are below.

  1. Open the terminal (found in /Applications/Utilities/)
  2. Type the following (without quotation marks) to show hidden files: “defaults write com.apple.finder AppleShowAllFiles -bool true”
  3. Hit enter
  4. Type the following (without quotation marks) to restart the Finder: “killall Finder”
  5. Hit enter

You can turn hidden files back off by doing the same thing, but switching the “true” to “false” in step 2.

