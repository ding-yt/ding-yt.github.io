---
layout: post
title:  Cancer genome analysis
date: 2015-11-22
desc:  Cancer genome analysis
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# Cancer genome analysis

For NGS whole genome or whole exome data 

  1. Alignment and data pre-processing
Use BWA MEM to do alignment Use Picard and GATK: mark duplicates -> realign around indel -> recalibration Note: BWA MEM only takes .fq file for alignment, can't take .bam file. No need for storing .sam file, just .bam file to save some space Realignment: GATK do this in two step, first create realignment targets list then do the realignment. When analyzing cancer data, it'd be better to generate target list with normal-tumor pair, then do realignment separately. It will result in some differences in raw SNP call if only generate realignment target list separately (sometimes not huge, some of my data give 0.1% more SNP when realign with both normal and tumor) 2\. SNP calling MuTect and VarScan are the best in some benchmark paper. But these two can only take normal-tumor pair sample. Can't do something like jointgenotyping in GATK. So a little inconvenient when comparing multiple samples. (MuTect use .bam as input. VarScan need pileup format which can be generate by samtools, but it's large and slow.) GATK can call raw SNP on each sample separately with HaplotypeCaller(GVCF mode), then do jointGenoTyping for all the samples together. But is not cancer specific. Platypus can also call on multiple samples together. DiscoSNP takes multiple samples too, but the input is .fq file. 
  1. Copy number variation
  2. Structure variation
