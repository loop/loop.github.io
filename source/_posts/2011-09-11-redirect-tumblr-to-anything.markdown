---
layout: post
title: Redirect Tumblr To Anything
tags:
- tumblr
- redirect
- javascript
---
I have a Tumblr blog which is my primary one but don't use it, I thought I
would just redirect it to google.com, did a quick search and found something
on StackExchange. It is a simple Javascript if statement.

    
    <script type="text/javascript">
    if(location.href == http://www.youraddress.tumblr.com/) location.replace(http://www.google.com);;
    </script>
    

