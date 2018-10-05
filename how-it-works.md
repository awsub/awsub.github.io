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

```
2018/10/04 14:53:46 [COMMAND]	Your tasks file is parsed and decoded to 2 job(s) ✅
2018/10/04 14:53:46 [COMMAND]	See logs here -> /Users/otiai10/proj/hotsub/github.io/helloworld_201810041451/log/20181004_145346
[hello.csv 0]	[CREATE]	Creating computing instance for this job...
[hello.csv 1]	[CREATE]	Creating computing instance for this job...
[hello.csv 1]	[CONSTRUCT]	Constructing containers for this job...
[hello.csv 1]	[CONSTRUCT]	Constructing workflow container inside the computing instance...
[hello.csv 1]	[CONSTRUCT]	Constructing routine container inside the computing instance...
[hello.csv 0]	[CONSTRUCT]	Constructing containers for this job...
[hello.csv 0]	[CONSTRUCT]	Constructing workflow container inside the computing instance...
[hello.csv 0]	[CONSTRUCT]	Constructing routine container inside the computing instance...
[hello.csv 0]	[EXECUTE]	&1> Hello! My name is Tom.
[hello.csv 0]	[EXECUTE]	&1> I'm a cat.
[hello.csv 1]	[EXECUTE]	&1> Hello! My name is Jerry.
[hello.csv 1]	[EXECUTE]	&1> I'm a mouse.
[hello.csv 0]	[DESTROY]	Terminating computing instance for this job...
[hello.csv 1]	[DESTROY]	Terminating computing instance for this job...
2018/10/04 15:00:03 [COMMAND]	All of your 2 job(s) are completed 🎉
```

Here explain what each step does and how it works.

# Lifecycle


First, you can see your task file (`csv`) is parsed as 2 tasks, because it has 2 rows except for the header row, and the log folder specified.

After that, each color represents each VM's lifecycle. It `CREATE` each VM, `CONSTRUCT` containers in it, `EXECUTE` the shell script you specified, and finally it `DESTROY` so that nothing remains after your jobs get done.
