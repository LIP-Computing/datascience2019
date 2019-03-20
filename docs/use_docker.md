---
title: Use docker with available images
layout: default
---

# Use docker with available images

First pull desired images from docker hub as explained in [Docker Images page](./docker_images.html).

To start docker image with Jupiter notebook:

```
docker run -it -p 8888:8888 -v /path_to_data:/data -v /path_to_notebooks:/notebooks lipcomputing/data_science_school_2019:<tag>
```

\<tag\> is one of the mentioned in [Docker Images page](./docker_images.html).

# Prepare images to be used offline

To save an image to a tar.gz file run:
```
docker save "lipcomputing/data_science_school_2019:<tag>" | gzip > "<image name>.tar.gz"
```
where "\<image name\>" is the file name.

# Load docker image offline

To load a previous saved image tar.gz file run:
```
gzip < "<image name>.tar.gz" | docker load
```

Then to start docker image with Jupyter notebook just run the same command mentioned before:
```
docker run -it -p 8888:8888 -v /path_to_data:/data -v /path_to_notebooks:/notebooks lipcomputing/data_science_school_2019:<tag>
```

[back](./)
