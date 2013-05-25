---
layout: post
title: How to Set Up SmartGit With GitHub
tags:
- GitHub
- Git
- Version Control
- How To
- Set Up
- GUI
- Windows
---
I've decided it is better for me to use a Git GUI for GitHub as I don't have much time to manage projects on Ubuntu and use command line. I've come across SmartGit, and it seems to be the best one for Windows out there.

I had a few issues to setting it up but I got it working. I've outlined what I did to make mine work. This is for anyone who is having trouble setting up their account using SmartGit.

  1. Download GIT For Windows (msysgit) – [http://code.google.com/p/msysgit/](http://code.google.com/p/msysgit/)
  2. Install msysgit choosing the following options:  Use git bash only [default].   Checkout Style:   Choose:  “check out as is commit as is”
  3. Launch GIT GUI
  4. In GIT GUI click menu item:  Help -> Show SSH Key -> Click Generate Key and enter a passphrase
  5. Confirm new RSA keys were created in C:\Users\YourUserName.ssh
  6. Open C:\Users\YourUserName.ssh\id_rsa.pub with Notepad++ and copy to clipboard.
  7. Login to Github and navigate to your Account Settings -> SSH public keys and Create a new key. Paste the contents of  your RSA public key you just copied.  Name it anything you want
  8. Download and Install SmartGIT – [http://www.syntevo.com/smartgit/index.html](http://www.syntevo.com/smartgit/index.html)
  9. Launch SmartGIT.  It should automatically find your rsa keys.
  10. Clone a project Project -> Clone -> Remote URL:  git@github.com:username/my-project.git
  11. If it asks for a password, use your github.com password, if it asks for your passphrase use the one you used on step D.