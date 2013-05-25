---
layout: post
title: Installing XAMPP On Ubuntu
tags:
- ubuntu
- localhost
- xampp
- installation
- server
- apache
---
Follow these simple steps to install XAMPP on Ubuntu:

  * Download XAMPP for Linux from [here](http://www.apachefriends.org/en/xampp-linux.html) and copy the tar.gz to the desktop.
  * Open up Terminal and type:
```
cd Desktop
sudo -s
tar xvfz xampp-linux-1.7.4.tar.gz -C /opt
```
  * Now when you try to copy anything to /opt/lampp/htdocs you will get permission denied. To fix this problem run this in Terminal:
  `chown username -R /opt/lampp/htdocs`

XAMPP is now installed! There is no GUI to start, stop and refresh XAMPP so to
start it type this in Terminal:

`/opt/lampp/lampp start`

To stop it's:

`/opt/lampp/lampp start`

For more parameters go [here](http://www.apachefriends.org/en/xampp-
linux.html#382).

Also to create password for FTP, MySQL etc run this in terminal and follow the
on screen instructions:

`sudo /opt/lampp/lampp security`

