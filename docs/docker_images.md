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
| gpu-py35-jnote-gwpy  | Keras, Tensorflow (NVIDIA), GWPY   | 3.5              |
| cpu-py36-jnote-gwpy  | Keras, Tensorflow, GWPY            | 3.5, 3.6         |
| gpu-py36-jnote-gwpy  | Keras, Tensorflow (NVIDIA), GWPY   | 3.5, 3.6         |

Details about using this images can be found on [use docker](./use_docker.html) or [use udocker](./use_udocker.html) pages.

To download this docker images from [official Docker Hub project page](https://hub.docker.com/r/lipcomputing/data_science_school_2019/tags) just select the desired tag and run the following command:

```
docker pull lipcomputing/data_science_school_2019:<tag>
```

where \<tag\> is one of the mentioned tags in above table.


## References

The base image for each build is provided by [Datmo](https://github.com/datmo/datmo/blob/master/README.md). They provide several workspaces configured with necessary software for each production model that data scientists need. They implemented some useful [concepts](https://datmo.readthedocs.io/en/latest/concepts.html) that allow better integration for each environment. They also implemented run concept comprised of tasks and snapshots.

Datmo also provides docker images with already preconfigured datmo workspaces and environments. For Data Science School we are using already generated docker images as base images:
  * datmo/keras-tensorflow:gpu-py35-notebook
  * datmo/keras-tensorflow:cpu-py35-notebook

This datmo images are used in each cpu/gpu image with python 3.5 and 3.6. Images with python 3.6 have all software installed for python 3.5. So to run with python 3.6 you need to run python36 and define [PYTHONPATH](https://docs.python.org/3/using/cmdline.html#envvar-PYTHONPATH) appending python 3.5 path, so all installed modules be available.

For more details about Datmo image features review their [README](https://github.com/datmo/datmo/blob/master/README.md).

The guide to setup the necessary environment is available on Datmo [DOCS](https://datmo.readthedocs.io/en/latest/env-setup.html).

For additional parameters and configurations to Jupyter notebook just check the available [documentation](https://jupyter-notebook.readthedocs.io/en/stable/config.html).

[back](./)