---
layout: post
title:  How to use BWA and SAMTools
date: 2015-01-12
desc:  How to use BWA and SAMTools
keywords: "blog"
categories: [Bioinfo,Software]
tags: "bioinfo,software"
icon: icon-html
---

# How to use BWA and SAMTools

Here is a nice tutorial with an example: http://icb.med.cornell.edu/wiki/index.php/Elementolab/BWA_tutorial 1\. Download BWA from http://bio-bwa.sourceforge.net, unzip, change directory to unzipped file and type 'make' (The things you downloaded are C source code. After make, an executable file BWA will be generated and BWA is ready for use.) 2\. Download a reference genome, here is one: http://hgdownload.cse.ucsc.edu/goldenPath/hg19/bigZips/hg38.chromFa.tar.gz (the Dec. 2013 (GRCh38/hg38) assembly of thehuman genome (hg38, GRCh38 Genome Reference Consortium Human Reference 38 (GCA_000001405.2)), hg38.chromFa.tar.gz - The assembly sequence in one file per chromosome. Repeats from RepeatMasker and Tandem Repeats Finder (with period of 12 or less) are shown in lower case; non-repeating sequence is shown in upper case.) 3\. Get your own sequencing data ready Before map the sequencing data to the reference genome, the ref genome need to be indexed first. 4\. Index the genome: bwa index refGenome.fa ( use 'bwa index -a bwtsw refGenome.fa' for human genome reference. bwtsw algorithm works with the whole human genome while the default one only works with ref genome. Also works with refGenome.fa.gz file) 5.alignment(3-5Gb RAM needed): paired-end: bwa mem ref.fa readsR1.fq.gz readsR2.fq.gz > aln-pe.sam BWA's work is done here. Then use samtools for further analysis. A tutorial of samtools:http://davetang.org/wiki/tiki-index.php?page=SAMTools http://biobits.org/samtools_primer.html 1\. convert SAM file to BAM file -> sort -> index: (BAM is binary version of SAM file, which is smaller and faster for analysis) samtools view -bhuS file.sam | samtools sort - file_prefix_sorted ( takes a .sam file, output a sorted .bam file: file_prefix_sorted.bam -u uncompressed, better for pipeline -b output format BAM -h include header -S input is SAM format default sorting by leftmost coordinates) samtools index file_sorted.bam (create index for a sorted BAM file: file_sorted.bam.bai) index the ref seq: samtools faidx ref.fa (ref.fa.fai will be created) 2\. call variable sites: ./samtools mpileup -uf / | /samtools-0.1.18/bcftools/bcftools view -bcg - > /samtools-0.1.18/bcftools/bcftools view > output.txt
