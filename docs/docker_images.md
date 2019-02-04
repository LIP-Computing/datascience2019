---
title: Docker Images
layout: default
---

# Docker Images

This year in March there will be the second edition of [Data Science School](http://www.lip.pt/data-science-2019/?p=school). The images provided in this project gives the necessary software to run the data challenges that will be presented to the attendees.

The images can be downloaded directly from [Docker Hub](https://hub.docker.com/r/lipcomputing/data_science_school_2019). In Docker Hub we provide multiple tags that present different software combinations, such as:

| Tag                  | Image details                      |  Python Version  |
|:---------------------|:-----------------------------------|:-----------------|
| cpu-py35-jnote-gwpy  | Keras, Tensorflow, GWPY            | 3.5              |
| cpu-py35-jnote-gwpy  | Keras, Tensorflow (NVIDIA), GWPY   | 3.5              |
| cpu-py36-jnote-gwpy  | Keras, Tensorflow, GWPY            | 3.5, 3.6         |
| cpu-py36-jnote-gwpy  | Keras, Tensorflow (NVIDIA), GWPY   | 3.5, 3.6         |

Details about using this images can be found on [use docker](./use_docker.html) or [use udocker](./use_udocker.html) pages.

To download this docker images from [official Docker Hub project page](https://hub.docker.com/r/lipcomputing/data_science_school_2019/tags) just select the desired tag and run the following command:

```
docker pull lipcomputing/data_science_school_2019:<tag>
```

where \<tag\> is one of the mentioned tags in above table.

[back](./)