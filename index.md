---
title: "Projects: cgpipe"
permalink: /
layout: home
#nav_gap: true
nav_order: 2
subsite: true
---

# cgpipe -- language for bioinformatics pipelines

CGpipe is a bioinformatics pipeline development language. It is very similar in spirit (and practice) to the venerable Makefile, but geared towards execution in an HPC environment. 

Like Makefiles, cgpipe pipelines establish a series of build targets, their required dependencies, and a recipe (shell script) used to build the outputs. 

Unlike Makefiles, cgpipe pipelines are executable scripts that can incorporate logic and flow control in the setup and execution of the build-graph. Additionally, cgpipe doesn't actually execute your job scripts -- instead, it submits these jobs to a proper job scheduler for efficient distributed processing across a computational cluster.

CGpipe is distributed as a self-executing fat-JAR file. This means that for installation, all one needs is a working copy of Java and the cgpipe file.

## History of cgpipe

CGpipe was written to support managing computational workflows in the study of pediatric cancers at [Stanford University](https://stanford.edu) and the [University of California San Francisco](https://ucsf.edu). For each patient sample sequenced, hundreds of jobs are generated and processed. This required the use of many different high-performance computing clusters over the years, including PBS, SGE, and SLURM clusters. The difficulty in migrating pipelines and adapting them to the different systems was one of the main motivations for cgpipe.

However, the major motivation was the desire to the the writing and use of complex pipelines as comparable to writing a simple shell script. For example, processing a single RNAseq sample may require 10's of jobs, but most of the logic is consistent between runs. There are a few variables (which FASTQ files to use, which reference genome, etc...), but for the most part, these can be handled with simple command line arguments. Then question then became -- how can we make something that works like this:

    $ ./rnaseq --fq1 input_R1.fastq --fq2 input_R2.fastq --ref GRCh38.fa --output sample1/

This is type of workflow that cgpipe was written to support. With this as the model, cgpipe has been refined over the years and has processed hundreds of thousands of jobs. If this is something that you need for data pipeline work, give it a try.

If you have any questions or find any issues with cgpipe, please [contact](https://compgen.io/contact) me!  
(Or submit an [issue](https://github.com/compgen-io/cgpipe/issues) on github!)

