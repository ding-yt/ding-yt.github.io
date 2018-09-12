---
layout: post
title:  SLURM queueing
date: 2014-11-05
desc:  SLURM queueing
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# SLURM queueing

simple.sh \--------------------------- #!/bin/sh #SBATCH - -output=test.log #SBATCH - -job-name=test1 ./myProgram \--------------------------- $sbatch simple.sh Check job squeue -u user Check node sinfo
