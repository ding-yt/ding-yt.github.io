---
layout: post
title:  R install package locally
date: 2017-05-18
desc:  R install package locally
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# R install package locally

install.packages("/dscrhome/yd44/software/ape_3.0-3.tar",repos = NULL, type="source",lib="/dscrhome/yd44/software/")   R CMD INSTALL -l lib/path package.tar
