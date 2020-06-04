---
layout: page
title: Quick version
permalink: /docs/getting-started/quick
parent: What is cgpipe?
grand_parent: Getting started

---

# The quick version...

CGpipe is langauge for defining and  building data analysis pipelines that run on an HPC cluster (for bioinformatics). The cgpipe program helps to submit jobs to the cluster and keeps track of jobs.

With cgpipe, a long set of submission scripts can be reduced to a single command. But, as a language, the pipelines you write are adaptable and configurable. This means that your single command can now work for a variety of situations.

So, instead of having a separate RNAseq script that is hard-coded for each project, you can now have one cgpipe script that accepts arguments for: different FASTQ files for input, different genome indexes, and any extra filtering steps. This will make your data pipelines easier to manage and more reproducible across multiple projects.