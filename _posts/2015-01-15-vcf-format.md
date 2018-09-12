---
layout: post
title:  SAM format and vcf format
date: 2015-01-15
desc:  SAM format and vcf format
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# SAM format and vcf format

SAM: mapping quality score: MapQ = -10 log10(P),Where P = probability that this mapping is NOT the correct one. MapQ = -10 log10(0.5) = 3; -10 log10(2/3)=1.76 (rounds to 2); which means the higher MapQ is, the better the mapping is, but 255 means not available. The score is transformed to a character in the QUAL field:QUAL = (-10 \log_{10}p) + 33 !"#$%&'()*+,-./0123456789:;?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~ P=10, 0.1 incorrect mapping (QUAL:+) P=20, 0.01 incorrect mapping (QUAL:5) (common cutoff) P=30, 0.001 incorrect mapping (QUAL:?) variant calling format PL value: ref ALT PL C G 55,3,0 means P(D|CC) = 10^(-5.5) = 3x10^(-6) P(D|CG) = 10^(-0.3) = 0.50 P(D|GG) = 10^(-0) = 1 REF=C and ALT=A,G, PL=7,0,37,13,40,49 means for the sample we are looking at, P(D|CC)=10^{-0.7}, P(D|CA)=1, P(D|AA)=10^{-3.7}, P(D|CG)=10^{-1.3}, P(D|AG)=1e-4 and P(D|GG)=10^{-4.9}. from: http://samtools.sourceforge.net/mpileup.shtml
