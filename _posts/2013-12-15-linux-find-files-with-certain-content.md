---
layout: post
title:  linux: find/replace files with certain content
date: 2013-12-15
desc:  linux: find/replace files with certain content
keywords: "blog"
categories: [Linux]
tags: "linux"
icon: icon-html
---

# linux: find/replace files with certain content

1\. find files with certain content find *.txt |xargs grep 'content' output: filename: content 2\. count number of files with this content find *.txt |xargs grep 'content'|wc -l 3\. replace certain content find *.txt |xargs perl -pi -e 's/string1/string2/'
