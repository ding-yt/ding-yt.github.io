---
layout: post
title:  Google test with Xcode
date: 2014-03-01
desc:  Google test with Xcode
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# Google test with Xcode

http://code.google.com/p/googletest/wiki/XcodeGuide 1\. download google test 2\. unzip, find `gtest.xcodeproj` in the `googletest-read-only/xcode/, open with xcode and build` 3\. find gtest.framework under /Users/Library/Developer/Xcode/DerivedData/gtest-frhitpysuwrikdawmkmigadpquls/Build/Products/Debug/   copy this to somewhere you want 4\. in a project where you want to use gTest, add new c++ class, include "gtest/gtest.h", and write your test code 5\. in build phases->link binary with libraries, add gtest.framwork; then click add build phase->copy files, add gtest.framework (need to do both, otherwise may give some error message like: image not found) 6\. build and go   More notes: add another target for testing, e.g. call it gtest when need to run the test, product->edit scheme, chose gtest instead of your main program as scheme, then click run. Now it only runs the tester but not the main program.
