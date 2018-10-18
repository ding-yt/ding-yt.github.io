---
layout:     post
title:      "grep and count lines for multiple files"
date:       2018-09-13 12:57:43
categories: linux
---
find . -name "*somefile" -print0 |xargs -0 grep -c "some pattern"
