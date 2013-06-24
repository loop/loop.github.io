---
layout: post
title: "Quick Start Guide to Setting Up Octopress From Tumblr"
date: 2013-06-24 13:09
comments: true
categories:
- Octopress
- Tumblr Migration
- GitHub Pages
- Guide
- Tumblr to Octopress
published: true
sharing: true
---
The title says a "Quick Start Guide" but this more of a full guide to fully migrate your tumblr blog to Octopress.

I've used Tumblr for the past 2 years as it was easy to set up and publish any content I wish to. It was easy to customise and best of all I didn't have to worry about the hosting solution but seeing as most of my posts are about code and development I decided to give [Octopress](http://octopress.org/) a try. This also gives me a chance to learn a bit of Ruby.

Migrating to Octopress was really easy with the [jekyll-import](https://github.com/jekyll/jekyll-import) gem. Even though the gem was fully provided, there was still some problems that came up. Here are the steps to make the migration go much more quickly. But before you start you should make sure you have installed Python and pip (this is a tool for easily installing and managing Python packages), here a [guide](http://docs.python-guide.org/en/latest/starting/install/osx.html) I used for Mountain Lion.

<ol>
<li>Setup Octopress following the <a href="http://octopress.org/docs/setup/">docs from Octopress</a>. This is relatively simple and shouldn't take too long.</li>
<li>Now this is the main part of the migration. Download the migration gem by running <code>gem install jekyll-import --pre</code></li>
<li>You also need to install json gem and Python's html2text package by running <code>gem install json</code> and <code>pip install html2text</code>. The html2text package is needed for the Tumblr HTML posts to be converted to Markdown which is the content writing language for Octopress.<br>
For some reason the html2text installation kept going wrong for me and kept throwing <code>failed with error code 1</code>.<br>
It turned out that I didn't have permission to install it.<br>
To fix this problem simply run <code>sudo pip install html2text</code>.<br>
Now if you try to run <code>which html2text</code> you should see the a path to the executable. If not, reinstall Python, html2text and check that you have updated your PYTHON_PATH env variable to pick up the html2text.</li>
<li>Download my modified <a href="https://gist.github.com/loop/5850220#file-tumblr-rb">tumblr.rb</a> script. Octopress uses <code>.markdown</code> extensions, the script needs to be modified a bit and also trunicates titles if they are over a 255 characters long. Place this file into <code>/usr/lib/ruby/gems/1.9.1/gems/jekyll0.11.2/lib/jekyll/migrators/</code></li>
<li>Now run:
```
ruby -rubygems -e 'require "jekyll/jekyll-import/tumblr"; JekyllImport::Tumblr.process(ruby -rubygems -e 'require "jekyll/jekyll-import/tumblr"; JekyllImport::Tumblr.process("http://yourtumblr.tumblr.com",format="markdown",grab_images=true)
```
  If you are getting the following error <code>Errno::ENOENT</code>, the fix for this a bit hackey but works. It works by creating symlinks:
    <ol>
    <li><code>cd to /usr/lib/ruby/gems/1.9.1/gems/jekyll0.11.2/lib/jekyll/migrators/</code></li>
    <li><code>cd ..</code></li>
    <li><code>ln -s %{TUMBLR_EXPORTED_POSTS_DIRECTORY}</code></li>
    <li><code>Run the migration command again</code></li>
    </ol>
</li>
<li>In your the folder you ran the command should now be your Tumblr posts in Markdown. Move these to <code>source/_posts</code> folder of your Octopress directory.</li>
<li><code>rake generate && rake deploy</code></li>
</ol>

####Redirect Tumblr URLs
Another step to fully migrate away from Tumblr is to fix the broken post links due to Tumblr's URL structure. This was an easy fix with **[Alias Generator for Posts](https://github.com/tsmango/jekyll_alias_generator)**. With this plugin you can specify and number of aliases for each post, but it has to be added to each posts YAML Front-matter.

Download the plugin and move `alias_generator.rb` to the `plugins` folder.
In the posts YAML matter add `alias: /post/10976876616/my-post`. This will redirect any request to `http://octopressblog.com/post/10976876616/my-post` to the post which contains this direct request. You can also give more than [one alias](https://github.com/tsmango/jekyll_alias_generator/blob/master/README.md).
