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

1. Setup Octopress following the [docs from Octopress](http://octopress.org/docs/setup/). This is relatively simple and shouldn't take too long.

2. Now this is the main part of the migration. Download the migration gem by running:

        gem install jekyll-import --pre

3. You also need to install json gem and Python's html2text package by running `gem install json` and `pip install html2text`. The html2text package is needed for the Tumblr HTML posts to be converted to Markdown which is the content writing language for Octopress.

   For some reason the html2text installation kept going wrong for me and kept throwing `failed with error code 1`.
   It turned out that I didn't have permission to install it. To fix this problem simply run `sudo pip install html2text`. Now if you try to run `which html2text` you should see the a path to the executable. If not, reinstall Python, html2text and check that you have updated your PYTHON_PATH env variable to pick up the html2text.

4. Download my modified [tumblr.rb](https://gist.github.com/loop/5850220#file-tumblr-rb) script. Octopress uses .markdown extensions, the script needs to be modified a bit and also trunicates titles if they are over a 255 characters long. Place this file into:

        /usr/lib/ruby/gems/1.9.1/gems/jekyll0.11.2/lib/jekyll/migrators/

5. Now run[^1]

        ruby -rubygems -e 'require "jekyll/jekyll-import/tumblr"; JekyllImport::Tumblr.process(ruby -rubygems -e 'require "jekyll/jekyll-import/tumblr"; JekyllImport::Tumblr.process("http://yourtumblr.tumblr.com",format="markdown",grab_images=true)

   If you are getting the following error `Errno::ENOENT`, the fix for this a bit hackey but works. It works by creating symlinks:
    1. cd to `/usr/lib/ruby/gems/1.9.1/gems/jekyll0.11.2/lib/jekyll/migrators/`
    2. `cd ..`
    3. `ln -s %{TUMBLR_EXPORTED_POSTS_DIRECTORY}`
    4. Run the migration command again.

   *Note: The jekyll gem directory may vary if you are using a different version.*

6. In your the folder you ran the command should now be your Tumblr posts in Markdown. Move these to `source/_posts` folder of your Octopress directory.

7. `rake generate && rake deploy`[^2]

####Redirect Tumblr URLs
Another step to fully migrate away from Tumblr is to fix the broken post links due to Tumblr's URL structure. This was an easy fix with **[Alias Generator for Posts](https://github.com/tsmango/jekyll_alias_generator)**. With this plugin you can specify and number of aliases for each post, but it has to be added to each posts YAML Front-matter.

Download the plugin and move `alias_generator.rb` to the `plugins` folder.
In the posts YAML matter add `alias: /post/10976876616/my-post`. This will redirect any request to `http://octopressblog.com/post/10976876616/my-post` to the post which contains this direct request. You can also give more than [one alias](https://github.com/tsmango/jekyll_alias_generator/blob/master/README.md).

[^1]:There are more arguments for this command but this one simply fetches the posts in .markdown extension and embeds all the images which are present in the Tumblr post. The image source will still be from Tumblr so you might want to download the images and do a find/replace as there isn't a script for that yet.
[^2]: Don't forget to git commit the source of your blog, otherwise if you lose it you won't be able to build your blog again and will have to start from scratch.