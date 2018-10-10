---
layout: default
title: How it works
permalink: /how-it-works
page_index: 1
---

> This page describes how `hotsub` works on cloud services, such as AWS.

# Example

As it's described in [Getting Started](/getting-started#2-hello-world), you can run a script on cloud instances by `run` command.

```
% hotsub run \
  --script hello.sh \
  --tasks hello.csv \
  --verbose
```

it will show following logs

![Example 001](/assets/img/example-001.png)

Here explains what each step does and how it works.

# Lifecycle

Basic lifecycle of `hotsub` execution is constructed by following steps.

1. Command parsing
2. `CREATE`: starting up VMs on cloud services (AWS EC2, by default)
3. `CONSTRUCT`: starting up Docker containers on the VMs
4. `FETCH`: downloading input files specified in `tasks` CSV file
5. `EXECUTE`: processing specified `script` file on the Docker containers
6. `PUSH`: uploading output files to the URL specified in `tasks` CSV file
6. `DESTROY`: terminating VM instances no longer used

First, you can see your task file (`csv`) is parsed as 2 tasks, because it has 2 rows except for the header row, and the log folder specified.

After that, each color represents each VM's lifecycle. It `CREATE` each VM, `CONSTRUCT` containers in it, `EXECUTE` the shell script you specified, and finally it `DESTROY` so that nothing remains after your jobs get done.
