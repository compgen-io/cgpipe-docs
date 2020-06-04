---
title: Home
permalink: /
layout: home
nav_order: 1
---

# cgpipe -- a language for bioinformatics pipelines

CGpipe is a bioinformatics pipeline development language. It is very similar in spirit (and practice) to the venerable Makefile, but geared towards execution in an HPC environment. 

Like Makefiles, cgpipe pipelines establish a series of build targets, their required dependencies, and a recipe (shell script) used to build the outputs. 

Unlike Makefiles, cgpipe pipelines are scripts that can incorporate logic and flow control in the setup and execution of the build-graph. Additionally, cgpipe doesn't actually execute your job scripts -- instead, it submits these jobs to a proper job scheduler for efficient distributed processing across a computational cluster.

CGpipe is distributed as a self-executing fat-JAR file. This means that for installation, all one needs is a working copy of Java and the cgpipe file.
