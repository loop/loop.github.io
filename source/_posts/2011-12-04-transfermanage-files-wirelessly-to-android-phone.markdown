---
layout: post
title: Transfer/Manage Files Wirelessly To Android Phone
tags:
- Android
- FTP
- Manage Files
- Remote Connection
- Wireless
- File Transfer
---
I'm really tired of trying to find my USB cable, I always seem to be misplace it. I believe the best way to transfer and manage your files from one device to another is doing it wirelessly.

I've found an awesome Android app called [SwiFTP FTP Server](https://market.android.com/details?id=org.swiftp&hl=en). Get it running on your phone and you can manage your entire files via a FTP client. The app is very simple and does what it says, nothing more nothing less. That's the way apps like this should be. I'm going to take you through getting this up and running.

Before you start make sure you have downloaded and installed [FileZilla Client](http://filezilla-project.org/download.php?type=client) on your computer. Also, make sure you have downloaded and installed [SwiFTP](https://market.android.com/details?id=org.swiftp&hl=en) app from the Android Market. Your phone and computer needs to be connected to the same local network for this to work.

**Setting up SwiFTP**

  1. Open the app.
  2. Tap **Setup**.
  3. Choose a **Username **and **Password **to use when connecting to your phone.
  4. Leave **Port number** as **2121**
  5. For the Stay within folder, I had a problem with this, initially I had **/sdcard** but when I tried connecting to it it would throw me an error on FileZilla. So if /sdcard doesn't work for you change it to **/mnt/sdcard** and it should work.
  6. Check **Accept connections from wifi**. (So you can connect to it when the phone is connected to your network.)
  7. I recommend enabling **Keep phone awake** so if you phone goes to sleep when you are connected the FTP connected isn't closed.
  8. Tap **Save**.
  9. Tap **Start**. 

**Connecting via FileZilla**

  1. Open FileZilla.
  2. Enter the Wifi URL IP address into host. So if mine is **[ftp://192.190.2.2:2121/](ftp://192.190.2.2:2121/)** for the IP address it would be **192.190.2.2**.
  3. Enter **Username **you chose when you initially set up the app.
  4. Enter **Password **you chose when you initially set up the app.
  5. For Port enter **2121**
  6. Click **Quickconnect**
  7. **BOOM!** All your Android files. Now do what you want, you can copy over files by dragging and dropping, and the usual stuff.

You can also use this app even if you aren't connected via your local network, in the setup check accept connections from net proxy. Make sure your password is secure as other people can connect to your phone if they find out your weak password. Read the app description on how the net proxy connection works.

