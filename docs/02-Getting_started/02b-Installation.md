---
layout: page
title: Installation
permalink: /docs/getting-started/installing
parent: Getting started
nav_order: 2
---

# Installation

*Note: CGpipe is intended to run on a Unix/Linux workstation, server, or cluster (including macOS).*

CGpipe is a Java program that is packaged as either a self-executing fat JAR 
file, or as an embeddable library. CGpipe is a Java program, but it has been 
developed to run on *nix-style hosts such as Mac OSX, FreeBSD or Linux. The 
only pre-requisite is a working installation of Java 1.7 or better. It is 
untested on Windows.


### Step 0: Install Java

Java version 7 or higher can be used. Install Java from your Linux distribution (using apt-get or yum), or see the [Oracle site](http://www.oracle.com/technetwork/java/javase/downloads/index.html) for more details.

### Step 1: Download cgpipe

You can download the `cgpipe` program from the [cgpipe releases](https://github.com/compgen-io/cgpipe/releases) website. You can save this file anywhere, but it is easiest to use if it is included on your `$PATH` somewhere, such as in `/usr/local/bin` or in a personal `$HOME/bin` directory.

### Step 2: Run a test pipeline

Most analysis pipelines you run will be custom written, however you can verify that your cgpipe installation is working with the following script:


	[hello.cgp]
	#!/usr/bin/env cgpipe

	print "Hello from cgpipe!"

This will load `cgpipe` from your path and execute the above script. Right now the script doesn't do anything other than
print a message to the console. If you save this as `hello.cgp` (and make it executable with `chmod +x hello.cgp`), you 
should see the following:

	$ ./hello.cgp
	Hello from cgpipe!

or...

	$ cgpipe hello.cgp
	Hello from cgpipe!

We will build from here to demonstate how to make your own pipelines in the next sections.

### Step 3: Configure cgpipe for your computing environment

CGpipe can run on a single user workstation, server, or HPC cluster. If you want to run more complex 
workflows by submitting jobs to a scheduler, it's necessary to configure cgpipe to use your scheduler. 
In cgpipe, job submission is handled by "job runners".

The currently supported job schedulers are: SBS, SGE, SLURM, or PBS. For more information about available 
runners, or the possible configuration settings, see "Running jobs".

If no scheduler is configured, jobs will be written as a bash script to stdout.

For information about how to configure cgpipe, see: [Configuring cgpipe](running#configuring-cgpipe).
