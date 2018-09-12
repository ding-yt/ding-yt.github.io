---
layout: post
title:  linux：scp
date: 2013-12-15
desc:  linux：scp
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# linux：scp

In file **~/.ssh/config** add: 
    
    
    Host hostname
        User username
        HostName hostaddress.com

then use **scp hostname:testdir/test.txt  localdir/**  to copy file use **scp -r hostname:testdir/dir  localdir/**  to copy directory   without replacing the existing files, use: rsync --ignore-existing ** hostname:testdir/*  localdir/**
