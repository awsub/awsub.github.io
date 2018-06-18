---
layout: default
title: Getting Started
permalink: /getting-started
---

> This page describes how to get started with `awsub` command. 

# 0. Prerequisites

- [docker-machine](#docker-machine)
- [AWS CLI](#aws-cli)
- [gcloud](https://cloud.google.com/sdk/install){:target="_blank"}, if you want to try `awsub` on GCP

## docker-machine

You can skip this step if following command already works well on your computer.

```sh
% docker-machine version
```

Otherwise, you need to install `docker-machine`.

- [Install Docker Machine - Docker Documentation](https://docs.docker.com/machine/install-machine/){:target="_blank"}
- **or** [Docker Toolbox overview - Docker Documentation](https://docs.docker.com/toolbox/overview)

## AWS CLI

You can skip this step if following command already works well on your computer.

```sh
% aws configure list
```

Otherwise, you need to install `awscli` and configure it with your credentials.

- [Installing the AWS Command Line Interface - AWS Command Line Interface](https://docs.aws.amazon.com/cli/latest/userguide/installing.html){:target="_blank"}
- **and** [Configuring the AWS CLI - AWS Command Line Interface ](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html){:target="_blank"}

# 1. Install awsub