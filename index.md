---
layout: default
permalink: /
---

# What is awsub?

`awsub` is a command line tool to execute batch jobs on cloud services, like AWS, GCP and so.   For example,

```sh
awsub --script ./hello.sh --tasks ./world.csv
```

This command will automatically launch several EC2 instances on AWS and execute your `./hello.sh` on the instances for each sample which is specified as a row in your `./world.csv`.

More details about what it does are explained in this page. Please check it out.

-> [How it works](/how-it-works)

# Why awsub?

`awsub` doesn't require any new knowledge to get started with. Only you need is shell script file you want to execute.

Launching VMs on cloud, provisionong, download and uploading files to storage are all automated by `awsub`.

There are more differences with other existing tools, check this page for more details.

-> [ETL and ExTL](/etl-and-extl)

# How to use?

You need `docker-machine` installed and `.aws/credentials` which can generate with `aws configure`.

For more friendly tutorial to get started, please check this page.

-> [Getting Started](/getting-started)
