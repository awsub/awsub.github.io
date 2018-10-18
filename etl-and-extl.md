---
layout: default
title: ETL and ExTL
permalink: /etl-and-extl
page_index: 3
---

> Here describes what ETL is and why **ExTL** is needed

# What is "ETL"

"ETL" is a data processing model generally used, not only for bio-informatics, in which data source, computing resources and output destination locations are separated.

// TODO: REFERENCE HERE

![](/assets/img/etl-general.png)

# "On-demand" ETL on Cloud

When it comes to Cloud, ETL can be effective way to use computing resources and file storage.

![](/assets/img/etl-adv.png)

[See animation of how "on-demand" ETL works ->](/assets/img/example-animated.gif)

# Huge reference files matter

It looks working fine, but in the context of bio-informatics, reference files are too large to handle as input files to be downloaded on every VM.

![](/assets/img/huge-reference.png)

# "ExTL": Extended ETL Framework

Here we suggest Extended ETL Framework, ExTL, to decrease inefficient network traffic and instance time to download such huge reference files.

![](/assets/img/extl-overview.png)

You can just add `--shared` flag to `hotsub` to make the resource shared.

```diff
$ hotsub run \
  --tasks  ./my-samples.csv \
  --script ./my-workflow.sh \
  --image  otiai10/STAR-alignment \
+ --shared REFERENCE=s3://bucket/huge/reference
```

# Advantage of ExTL over ETL

As "ExTL" creates an additional instance than computing VM instances, when it's large number of concurrent jobs, ExTL has an advantage over ETL.

Fig. Time for computing by concurrency.

![](/assets/img/compute-time.png)

Fig. Estimated prices by concurrency.

![](/assets/img/advantage.png)

See [Poster on GCCBOSC 2018](https://github.com/hotsub/lab/blob/master/publications/2018-06-28_GCCBOSC/Poster-bosc2018.pdf) for more details.
