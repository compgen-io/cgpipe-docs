---
layout: page
title: Job log
permalink: /docs/features/job-log
parent: Features
---

# Job log

This job log is a feature that helps to coordinate different pipelines running on the same dataset.

Fundamentally, the job-log is a text file that contains a list of each job that was submitted to the scheduler for a given project.

## Use case

For example, you may want to split your analysis into different sections. For example, 

1. aligning FASTQ data to a genome  
2. post-processing the data  
3. calling variants

These are three separate pipelines could be completely separate scripts. However, for a given project, it might make sense to process them in this order. Without using a job-log, you have two main options:

1. Combine all the steps into one monolithic pipeline, or
2. Run each step separately, waiting until the first was done to execute the second, etc...

One problem with the first approach is that you now have to manage each step in one large pipeline -- one for each project. But what happens if you want to change one of the steps? Let's say you want to change the alignment program... now you need to change this pipeline code in each monolithic pipeline, for each project. This would lead to a lot of repeated effort.

The second approach fixes the first issue -- repeated code -- but at the expense of efficiency. When you have all of steps in a monolithic list, each job submitted to the scheduler at the same time. This means that the jobs can be scheduled as efficiently as possible. If you have to wait for multiple steps to finish before submitting jobs, you could end up with idle cluster time, or delayed priorities for submitted jobs.

*Note: there is a third option, where you create pipeline steps like libraries or functions. Then you could effectively import the steps you need, but this is very heavily dependent upon the pipeline manager. CGpipe does support this method, but using the job-log is still recommended.*

