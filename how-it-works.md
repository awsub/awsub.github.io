---
layout: default
title: How it works
permalink: /how-it-works
page_index: 1
---

> This page describes how `hotsub` works on cloud services, such as AWS.

First, you can see your task file (`csv`) is parsed as 2 tasks, because it has 2 rows except for the header row, and the log folder specified.

After that, each color represents each VM's lifecycle. It `CREATE` each VM, `CONSTRUCT` containers in it, `EXECUTE` the shell script you specified, and finally it `DESTROY` so that nothing remains after your jobs get done.
