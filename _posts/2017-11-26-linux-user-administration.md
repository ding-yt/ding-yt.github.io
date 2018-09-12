---
layout: post
title:  "linux user administration"
date:   2017-11-26
keywords: "linux"
categories: [Linux]
tags: [linux]
icon: icon-html
author: ytDing
post_id: 269
comment_status: open
status: publish
---



# linux user administration

If you have root access and want to mange users: To create user and set pass word: 

> >useradd [username] >passwd [username]

To give this user sudo access: 

  1. edit /etc/sudoers file. There will be one line like this:

> ## Allows people in group wheel to run all commands #wheel   ALL=(ALL)       ALL

  remove the "#", now wheel group can run sudo 2.add user to wheel group will give them sudo access: 

> > sudo usermod -aG wheel [username]
