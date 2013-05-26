---
layout: post
title: wgetting a Website
tags:
- download
- command line
- wget
- website
alias: /post/7461036665/wgetting-a-website
---
`wget -m -p -P ~/website example.com`

(let it do it's stuff)

`rsync -avz --delete ~/website/ me@domain.com:path/of/website`

