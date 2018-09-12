---
layout: post
title:  GitHub add repo remotely from server
date: 2018-07-27
desc:  GitHub add repo remotely from server
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# GitHub add repo remotely from server

curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}
    
    
    # Remember replace USER with your username and REPO with your repository/application name!
    git remote add origin git@github.com:USER/REPO.git
    git push origin master
    
    ref:https://stackoverflow.com/questions/2423777/is-it-possible-to-create-a-remote-repo-on-github-from-the-cli-without-opening-br
