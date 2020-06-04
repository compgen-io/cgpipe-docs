---
layout: page
title:  About
permalink: /about
nav_order: 10001
nav_gap: true
---

# History of cgpipe

CGpipe was written by Marcus Breese, PhD to support managing computational workflows in the study of pediatric cancers at [Stanford University](https://stanford.edu) and the [University of California San Francisco](https://ucsf.edu). For each patient sample sequenced, hundreds of jobs are generated and processed. This required the use of many different high-performance computing clusters over the years, including PBS, SGE, and SLURM clusters. The difficulty in migrating pipelines and adapting them to the different systems was one of the main motivations for cgpipe.

However, the major motivation was the desire to the the writing and use of complex pipelines as comparable to writing a simple shell script. For example, processing a single RNAseq sample may require 10's of jobs, but most of the logic is consistent between runs. There are a few variables (which FASTQ files to use, which reference genome, etc...), but for the most part, these can be handled with simple command line arguments. Then question then became -- how can we make something that works like this:

    $ ./rnaseq --fq1 input_R1.fastq --fq2 input_R2.fastq --ref GRCh38.fa --output sample1/

This is type of dataflow that cgpipe was written to support. With this as the model, cgpipe has refined over the years to process hundreds of thousands of jobs. If this is something that you need for data pipeline work, give it a try.

If you have any questions or find any issues with cgpipe, please [contact](contact) me!  
(Or submit an [issue](https://github.com/compgen-io/cgpipe/issues) on github!)

