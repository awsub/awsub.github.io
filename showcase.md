---
layout: default
title: Examples Showcase
permalink: /showcase
page_index: 2
sublinks:
  - title: BWA alignment
    link: bwa-alignment
  - title: STAR alignment
    link: star-alignment
---

> Here describes commonly-used examples as showcase.

# BWA alignment

```sh
% hotsub run \
    --tasks ./bwa-alignment.csv \
    --script ./main.sh \
    --image otiai10/bwa \
    --aws-ec2-instance-type t2.large \
    --verbose
```

For more details: [https://github.com/otiai10/hotsub/tree/master/examples/BWA](https://github.com/otiai10/hotsub/tree/master/examples/BWA)

# STAR alignment

```sh
hotsub run \
  --tasks ./star-alignment.csv \
  --script ./main.sh \
  --image friend1ws/star-alignment \
  --aws-ec2-instance-type m4.2xlarge \
  --disk-size 128 \
  --verbose
```

For more details [https://github.com/otiai10/hotsub/tree/master/examples/STAR](https://github.com/otiai10/hotsub/tree/master/examples/STAR)
