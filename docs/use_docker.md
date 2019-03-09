---
title: Use docker with available images
layout: default
---

# Use docker with available images

First pull desired images from docker hub as explaned in [Docker Images page](./docker_images.html).

To start docker image with Jupiter notebook:

```
docker run -it -p 8888:8888 -v /path_to_data:/data -v /path_to_notebooks:/notebooks lipcomputing/data_science_school_2019:<tag>
```

\<tag\> is one of the mentioned in [Docker Images page](./docker_images.html).

[back](./)
