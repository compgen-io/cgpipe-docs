---
layout: page
title: Running cgpipe
permalink: /docs/getting-started/running
parent: Getting started
nav_order: 3
---

# Running cgpipe
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Using the program

CGpipe can be run either from the command-line (`cgpipe mypipeline.cgp`). Or, it can be used in a pipeline script that starts with a shebang (`!#`) -- just like any other scripting language! It is also recommended to copy cgpipe to a location in your `$PATH`. This way, you can use the following stub to start your script:

    #!/usr/bin/env cgpipe
    print "Hello pipeline!"

> *In most cases, you won't be executing cgpipe directly. Instead, you'll be writing pipeline scripts in cgpipe, and **those** are what you'll execute.*


## Configuring cgpipe

CGpipe configuration or job variables can be set on a per-run, per-user, or 
per-server basis. At startup, cgpipe looks for configuration information in the following
locations (in order of preference):

1. From within the cgpipe JAR itself (path `io/compgen/cgpipe/cgpiperc` -- this is only for default values),
1. `/etc/cgpiperc` (for server-level options), 
1. `$CGPIPE_HOME/.cgpiperc` (CGPIPE_HOME defaults to the directory containing the cgpipe binary), 
1. `~/.cgpiperc` (user-local config),
1. The environmental variable `CGPIPE_ENV` (semi-colon delimited)

All of these configuration files are themselves cgpipe scripts that are 'included' with your running cgpipe script. This means that they can inherit options from each other.

## Examples

* Do you want to set `job.mail` for all of your personal scripts? Then set the value in `~/.cgpiperc`. 
* Do you want to configure the batch scheduler settings for everyone on a given system? Then set `job.runner` in
 `/etc/cgpiperc`.
     * What is cgpipe is installed as an envirnmental module? Then use `$CGPIPE_HOME/.cgpiperc`. 
* Do you have cgpipe installed on a network drive that is mounted on different clusters? You 
can still set the cgpipe runner config from `$CGPIPE_HOME/.cgpiperc` by setting the `job.runner` config values. But, you can also
use if/then/endif blocks to set system specifc values. The cgpiperc files are full scripts that are interpretted, so you can make them quite customizeable.

> *I've actually had to do this. We had a network drive that was shared between two different clusters. One was running CentOS 6 + PBS, the other was CentOS 7 + SGE. And, of course, the same pipelines had to be able to run on both clusters.*
