---
layout: post
title:  Gnuplot no pdf terminal
date: 2015-11-27
desc:  Gnuplot no pdf terminal
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# Gnuplot no pdf terminal

Use postscript then convert with ps2pdf 
    
    
    set term postscript eps enhanced color 
    set output '|ps2pdf - outputfile.pdf'
