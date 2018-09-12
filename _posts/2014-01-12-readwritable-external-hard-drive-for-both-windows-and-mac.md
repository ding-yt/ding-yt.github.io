---
layout: post
title:  read/writable external hard drive for both windows and mac
date: 2014-01-12
desc:  read/writable external hard drive for both windows and mac
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# read/writable external hard drive for both windows and mac

**Use format: exFAT  (+ Mac OS Extended Journaled for time machine backup) !!**

Other formats:

FAT: can be read and wrote by both windows and mac, but has a single file size up limit -- 4G (not good for videos like blue-ray)

NTFS: while windows can do both, mac can only read but not write

Mac OS Extended (Journaled): mac only, windows can't even see it without certain software. But mac time machine only take this format.

exFAT: read and write by both OS, no single file size limit

So partition the external hard drive to at least 2 part, one in Mac OS Extended (Journaled) for time machine backup, the other in exFAT for data exchange between mac and windows. Mission accomplished!
