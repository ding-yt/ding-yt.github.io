---
layout: post
title:  "Install Sambamba"
date:   2017-02-15
desc: "Install Sambamba"
keywords: "linux,bioinfo,software"
categories: [Bioinfo]
tags: [linux,bioinfo,software]
icon: icon-html
---


# Install Sambamba

Sambamba is supposed to be faster than sam when dealing with .bam/.sam files. 1\. install idc https://github.com/ldc-developers/ldc No need to compile. Just add ..idc/bin  .. idc/lib to path: 
    
    
    export PATH=~/ldc2-0.17.1-linux-x86_64/bin/:$PATH
    export LIBRARY_PATH=~/ldc2-0.17.1-linux-x86_64/lib/

  2\. install sambamba https://github.com/lomereiter/sambamba 
    
    
    make sambamba-ldmd2-64

  3\. use sambamba to do subsampling 
    
    
    ~/src/sambamba/sambamba_v0.3.3 view -h -t $numThreads -s $fractionOfReads -f bam --subsampling-seed=$seed $testBam -o $subsampledTestBam
