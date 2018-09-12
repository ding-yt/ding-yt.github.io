---
layout: post
title:  bash script read file line by line
date: 2015-11-25
desc:  bash script read file line by line
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# bash script read file line by line

#!/bin/bash filename="somefile.txt" while read -r line do name=$line echo "Name read from file: $name" #can do something more on each file here done <"$filename"     Read a line into a parameter: par=$(sed -n "${i}p" par.txt)
