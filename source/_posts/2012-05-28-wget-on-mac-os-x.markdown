---
layout: post
title: wget on Mac OS X
tags:
- how to
- wget
- mac os x
- installation
---
When I tried to make a local mirror of a site I was surprised to find out that wget is not installed by default on the OS X.

I looked around for a solution and most of them say to install MacPorts or something other silly things. In the end I found a easy way to install wget, before you install it using this method you need to have [Xcode](http://itunes.apple.com/us/app/xcode/id497799835?ls=1&mt=12) as it has some prerequisites required for installing wget.

To install wget run these commands in Terminal:

  1. Downloads the source.

    `curl -O http://ftp.gnu.org/gnu/wget/wget-1.13.4.tar.gz`

  2. Uncompress the source.

    `tar -xzf wget-1.13.4.tar.gz`

  3. Change directory into the source.

    `cd wget-1.13.4`

  4. Changes a few settings to prevent a “GNUTLS not available” error.

    `./configure --with-ssl=openssl`

  5. Builds the source.

    `make`

  6. Installs wget.

    `sudo make install`

  7. Check to see wget is installed correctly.

    `wget --help`

  8. Clean up by removing the wget download files.

    `cd .. && rm -rf wget*`

**P.S.** It would be pretty awesome if you followed me on Twitter, [here](http://twitter.com/finitepost).

