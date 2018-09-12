---
layout: post
title:  compress multiple files into one .gz in Linux
date: 2015-09-27
desc:  compress multiple files into one .gz in Linux
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# compress multiple files into one .gz in Linux

Compress: tar -cf - list_of_file_names | gzip > output_file.tar.gz Uncompress: gzip -dc output_file.tar.gz | tar -xf -
